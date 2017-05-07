# KFC
it's a task
Kfc套餐包括如下角色：
MealBuilder：抽象建造者
SubMealBuilderA，SubMealBuilderB：具体建造者A、B，实现接口，具体化各个部分的创建
KFCWalter：服务员，调用具体建造者来创建复杂对象的各个对象
Meal ：套餐组成基本元素
//产品类定义
Public class Meal{
  Private String food;
  Private String drink;
  
  Public void setfood(String food){
  This.food=food;
  }
  Public String getfood(){
     Return food; 
   }
  Public void setdrink(String drink){
  This.drink=drink;
  }
  Public String getdrink(){
     Return drink;
  } 

}


//建造者抽象类定义
Public abstract class MealBulider{
  Private Meal meal = new Meal();
  public void bulidFood();
  public void bulidDrink();
  Public Meal getMeal(){
   Return new Meal();
  }
}

//具体建造者定义
Public class SubMealBuilderA extends MealBuilder{
  Pubilc void buildFood(){
   //System.out.println(“一个汉堡”);
   meal.setFood("一个汉堡");
}
 Pubilc void buildDrink(){
   //System.out.println(“一杯冰可乐”);
  meal.setDrink("一杯冰可乐");
 }

}

Public class SubMealBuilderB  extends MealBuilder{
  Pubilc void buildFood(){
   //System.out.println(“一份薯条”);
  meal.setFood("一份薯条");
     }
Pubilc void buildDrink(){
   //System.out.println(“一杯奶茶”);
   Meal.setDrink("一杯奶茶"); 
 }

}

//服务员定义
Public class KFCWalter{
  Private MealBuilder mb;
  Public void setMealbuilder(MealBuilder mb){
       This.mb = mb;

  }
  Public Meal construct(){

mb.buildFood();
mb.buildDrink();
Return mb.getMeal();
  }
}
//客户端类定义
Public static void main(String[] args){
  KCFWalter Walter= new  KCFWalter();
  System.out.println(“=====套餐A====”);
  MealBuilder  A = new SubMealBuilderA();
  Walter.setMealBuilder(A);
  Walter.construct();
  System.out.println(“=====套餐B====”);
  MealBuilder  B = new SubMealBuilderB();
  Walter.setMealBuilder(B);
  Walter.construct();

}


kfc套餐能使用工厂方法模式与建造者模式结合。
在建造者模式中，客户端不必知道产品内部组成的细节，将产品本身与产品的创建过程解耦，使得相同的创建过程可以创建不同的产品对象。
这符合kfc套餐从套餐生产，组合最后由服务员配发给客户这几个复杂的过程。
而加入工厂方法模式则是精细了生产这个过程（即Meal这一部分），有利于形成更多的套餐。
