package machine;
import java.util.Scanner;
import java.util.Objects;

public class CoffeeMachine {
       public static void main(String[] args) {
         int water = 400;
         int milk = 540;
         int beans = 120;
         int cups = 9;
         int money = 550;
        action( water , milk , beans , cups , money );
    }


    static void machineContent(int water, int milk, int beans , int cups , int money) {
        System.out.format("""
                The coffee machine has:
                %d ml of water
                %d ml of milk
                %d g of coffee beans
                %d disposable cups
                $%d of money
                """, water , milk , beans , cups , money);
    }
    static void checkIfEnough(int water,int beans,int milk,int cups, int money , int coffeeType){
        String item ="";
        if (water <= 0 ) {
            item = "water";
        } else if (beans <= 0) {
            item = "coffee beans";
        } else if (milk<= 0) {
            item = "milk";
        } else if (cups <= 0) {
            item = "disposable cups" ;
        }
        if (water>0 && beans>0 && milk >0&&cups>0) {
            System.out.println("I have enough resources, making you a coffee!");
        } else {
            System.out.format("Sorry, not enough %s!\n", item);
            if (coffeeType == 1) {
                water += 250;
                beans += 16;
                money -= 4;
                cups += 1;
            } else if (coffeeType == 2) {
                water += 350;
                milk += 75;
                beans += 20;
                money -= 7;
                cups += 1;
            }else {
                water += 200;
                milk += 100;
                beans += 12;
                money -= 6;
                cups += 1;
            }
            action(water,milk,beans,cups,money);
        }
    }
    static void action( int water, int milk, int beans , int cups , int money ){
        Scanner scanner = new Scanner(System.in);
        String action = "";
        while (!Objects.equals(action, "exit")){
            System.out.println("Write action (buy, fill, take, remaining, exit): ");
            action = scanner.next();
            switch (action) {
                case "buy" -> {
                    System.out.println("What do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino:");
                    String coffee = scanner.next();
                    switch (coffee) {
                        case "1" -> {
                            checkIfEnough(water - 250, beans - 16, milk, cups - 1, money + 4, 1);
                            water -= 250;
                            beans -= 16;
                            money += 4;
                            cups -= 1;
                        }
                        case "2" -> {
                            checkIfEnough(water - 350, beans - 20, milk - 75, cups - 1, money + 7, 2);
                            water -= 350;
                            milk -= 75;
                            beans -= 20;
                            money += 7;
                            cups -= 1;
                        }
                        case "3" -> {
                            checkIfEnough(water - 200, beans - 12, milk - 100, cups - 1, money + 6, 3);
                            water -= 200;
                            milk -= 100;
                            beans -= 12;
                            money += 6;
                            cups -= 1;
                        }
                        case "back" -> action(water,milk, beans, cups, money);
                        default -> {
                        }
                    }
                }
                case "fill" -> {
                    System.out.println("Write how many ml of water to add:");
                    water += scanner.nextInt();
                    System.out.println("Write how many ml of milk the coffee to add:");
                    milk += scanner.nextInt();
                    System.out.println("Write how many grams of coffee beans to add: ");
                    beans += scanner.nextInt();
                    System.out.println("Write how many disposable cups of coffee you want to add: ");
                    cups += scanner.nextInt();
                }
                case "take" -> {
                    System.out.println("I gave you $" + money);
                    money = 0;
                }
                case "remaining" -> machineContent(water, milk, beans, cups, money);

                case "exit" -> System.exit(0);

                default -> {
                }
            }

        }
    }
}
