# Fast-Food
Fast Food Game
import java.util.Random;

/**
 * Write a description of class Item here.
 *
 * @author (your name)
 * @version (a version number or a date)
 */
public class Item
{
    private int itemNo;
    private int hp;
    private int atk;
    private int def;
    private int spd;
    private int luck;
    private String name;
    private String desc;
    private String stats;
    /**
     * Constructor for objects of class Enemy
     */
    public Item(int i)
    {
        itemNo = i;
        int x = 0;
        switch (i) 
        {
            case 1:  name = "Buffalo Chicken Pizza.";
                     hp=-50; atk=20; def=0; spd=10; luck=0;
                     desc = "No.";
                     break;
                     
            case 2:  name = "Cinnamon Roll.";
                     hp=75; atk=0; def=0; spd=25; luck=0;
                     desc = "A warm roll with cinnamon and frosting. Delicous.";
                     break;
                     
            case 3:  name = "Brownie.";
                     hp=75; atk=0; def=0; spd=20; luck=5;
                     desc = "Chocolate pastry with a light dusting of powdered sugar.";
                     break;
                     
            case 4:  name = "Hawaiian Pizza.";
                     hp=100; atk=5; def=5; spd=5; luck=0;
                     desc = "Pineapple on pizza? Delicous.";
                     break;
                     
            case 5:  name = "Pasta with Alfredo Sauce.";
                     hp=100; atk=0; def=10; spd=0; luck=0;
                     desc = "Pasta in a cheese sauce.";
                     break;
                     
            case 6:  name = "Pasta with Tomato Sauce.";
                     hp=100; atk=10; def=0; spd=0; luck=0;
                     desc = "Pasta in a savory red sauce.";
                     break;
                     
            case 7:  name = "Cheese Pizza.";
                     hp=150; atk=5; def=5; spd=0; luck=0;
                     desc = "The classic.";
                     break;
                     
            case 8:  name = "Pepperoni.";
                     hp=150; atk=10; def=0; spd=0; luck=0;
                     desc = "The classic 2.0";
                     break;
                     
            case 9:  name = "Spinach Pizza.";
                     hp=300; atk=0; def=20; spd=0; luck=0;
                     desc = "It's good no joke.";
                     break;
                     
            case 10: name = "Alfredo Mushroom Chicken Pizza.";
                     hp=200; atk=0; def=0; spd=0; luck=10;
                     desc  = "In my opinion which is 100% fact the best tasting pizza.";
                     break;
                     
            case 11: name = "Chicken Noodle Soup.";
                     hp=200; atk=10; def=0; spd=0; luck=5;
                     desc = "Hearty and filling.";
                     break;
                     
            case 12: name = "Garlic Cheesy Bread.";
                     hp=75; atk=0; def=5; spd=0; luck=0;
                     desc = "If you're a vampire please beware.";
                     break;
        }
        stats = ("Hp: "+hp+ "Atk: "+atk+ "Def: "+ def + "Speed: " + spd + "Luck: " + luck + ".");
    }
    public int getAtk()
    {
       return atk;
    }
    public int getDef()
    {
       return def;
    }
    public int getHp()
    {
       return hp;
    }
    public int getSpd()
    {
       return spd;
    }
    public int getLuck()
    {
       return luck;
    }
    public String getName()
    {
        return name;
    }
    public String getDesc()
    {
        return desc;
    }
    public String getStats()
    {
        return stats;
    }
    
    public void setAtk(int a)
    {
        atk = a;
    }
    public void setDef(int d)
    {
        def = d;
    }
    public void setHp(int h)
    {
        hp = h;
    }
    public void setSpd(int s)
    {
        spd = s;
    }
    public void setLuck(int l)
    {
        luck = l;
    }
    
}
///////////////////////////////////
import java.util.Random;
/**
 * Write a description of class Player here.
 *
 * @author Kenneth Chen
 * @version 8/20/18
 */
public class Player
{
    // instance variables - replace the example below with your own
    private int level;
    private int hp;
    private int atk;
    private int def;
    private int spd;
    private int luck;
    private int xp;
    private int gold;
    private boolean alive = true;
    /**
     * Constructor for objects of class Enemy
     */
    public Player(int a, int d, int s, int l)
    {
        hp = 10;
        atk = a;
        def = d;
        spd = s;
        luck = l;
        xp = 0;
        level = 1;
        gold = 20;
    }
    
    public boolean getAlive()
    {
        return alive;
    }
    public int getGold()
    {
        return gold;
    }
    public int getLv()
    {
        return level;
    }
    public int getXp()
    {
        return xp;
    }
    public int getAtk()
    {
       return atk;
    }
    public int getDef()
    {
       return def;
    }
    public int getHp()
    {
       return hp;
    }
    public int getSpd()
    {
       return spd;
    }
    public int getLuck()
    {
       return luck;
    }
   
    public void setGold(int g)
    {
        gold = g;
    }
    public void setLv(int lv)
    {
        level = lv;
    }
    public void setXp(int x)
    {
        xp = x;
        if ((xp >= (20*level)) && level <= 20)
        {
            levelUp();
        }
    }
    public void setAtk(int a)
    {
        atk = a;
    }
    public void setDef(int d)
    {
        def = d;
    }
    public void setHp(int h)
    {
        hp = h;
         if (hp <= 0)
        {
            death();
        }
    }
    public void setSpd(int s)
    {
        spd = s;
    }
    public void setLuck(int l)
    {
        luck = l;
    }
    //////////////////////////////////////////////////////////////////////////////////////////////
    public void levelUp()
    {
        Random rand = new Random();
        xp = xp - (20*level);
        level++;
        atk += rand.nextInt(3) + 1;
        def += rand.nextInt(3) + 1;
        hp = level*10;
        spd += rand.nextInt(3) + 1;
        luck += rand.nextInt(2) + 1;
    }
   
    public void death()
    {
        alive = false;
    }
    public void eat(Item a)
    {
        atk+= a.getAtk();
        def+= a.getDef();
        hp+= a.getHp();
        if (hp > level*25)
        {
            hp = level*25;
        }
        luck+= a.getLuck();
        spd+= a.getSpd();
    }
    public void levelCheat(int a)
    {
        for (int i = 0; i < a; i++)
        {
            levelUp();
        }
    }
}
/////////////////////
 import java.util.Random;
/**
 * Enemy Template
 *
 * @author Kenneth Chen
 * @version 8/20/1
 */
public class Enemy
{
    // instance variables - replace the example below with your own
    private int monsterNo;
    private int hp;
    private int atk;
    private int def;
    private int spd;
    private int luck;
    private int level;
    private int xp;
    private boolean alive;
    private String name;
    private String desc;
    private int gold;
    /**
     * Constructor for objects of class Enemy
     */
    public Enemy(int monNo, int lv, int g, int x, int h, int a, int d, int s, int l)
    {
        hp = h;
        atk = a;
        def = d;
        spd = s;
        luck = l;
        gold = g;
        xp = x;
        level = lv;
        alive = true;
         switch (monNo) 
            {
            case 1:  name = "Rabbit";
                     desc = "A little white bunny munching on a baby carrot. Once did time for stabbing someone 37 times in the chest.";
                     break;
                     
            case 2:  name = "Slime"; 
                     desc = "A cute and squishy gelatinous blob. Really likes pumpkin pie.";
                     break;
                     
            case 3:  name = "Ogre"; 
                     desc = "A large humanoid with a massive appetite. Has 3 kids and is currently workng 5 jobs to pay for their college fund.";
                     break;
                     
            case 4:  name = "Haunted Armor";
                     desc = "A suit of armor possessed by a wandering spirit. His friends never invite to hide and seek because he creaks too much.";
                     break;
                     
            case 5:  name = "Cyclops";
                     desc = "A savage one-eyed giant wielding a vicious wooden club. Has a prescription monocle.";
                     break;
                     
            case 6:  name = "Djinn";
                     desc = "An ancient spirit from the middle east. In love with Basilisk. Usually invisible, but is blushing too hard to notice that he's turned red.";
                     break;
                     
            case 7:  name = "Kumiho";
                     desc = "A long-lived fox spirit capable of shapeshifting into various forms, usually of alluring women. Sick of being confused for a kitsune";
                     break;
                     
            case 8:  name = "Centaur";
                     desc = "A creature with the torso of a human and the lower half of a horse. Minotaur is his drinking buddy.";
                     break;
                     
            case 9:  name = "Rabid Wolf";
                     desc = "A normal wolf driven mad by rabies. Extremely dangerous, so beware";
                     break;
                     
            case 10: name = "Basilisk";
                     desc = "The Queen of Snakes. Can't look into mirror so she thinks she's ugly and unloved. Has a secret admirer... ";
                     break;
                     
            case 11: name = "Minotaur";
                     desc = "A creature with the body of a man and the head of a bull. Really likes pita bread. Can't hold his alcohol.";
                     break;
                     
            case 12: name = "Dragon";
                     desc = "A legendary beast who once destroyed entire kingdoms in mere hours. Spends most of his time doing crossword puzzles and eating pizza.";
                     break;
        }
    }
     /**
     * Constructor for objects of class Enemy
     */
    public Enemy(int monNo, int lv)
    {
        for (int i = 0; i < lv; i++)
        {
            Random rand = new Random();
            atk += rand.nextInt(3) + 1;
            def += rand.nextInt(3) + 1;
            spd += rand.nextInt(3) + 1;
            hp += rand.nextInt(15) + 1;
        }
        luck = 10;
        gold = lv*2;
        xp = lv*25;
        alive = true;
         switch (monNo) 
            {
            case 1:  name = "Rabbit";
                     desc = "A little white bunny munching on a baby carrot. Once did time for stabbing someone 37 times in the chest.";
                     break;
                     
            case 2:  name = "Slime"; 
                     desc = "A cute and squishy gelatinous blob. Really likes pumpkin pie.";
                     break;
                     
            case 3:  name = "Ogre"; 
                     desc = "A large humanoid with a massive appetite. Has 3 kids and is currently workng 5 jobs to pay for their college fund.";
                     break;
                     
            case 4:  name = "Haunted Armor";
                     desc = "A suit of armor possessed by a wandering spirit. His friends never invite to hide and seek because he creaks too much.";
                     break;
                     
            case 5:  name = "Cyclops";
                     desc = "A savage one-eyed giant wielding a vicious wooden club. Has a prescription monocle.";
                     break;
                     
            case 6:  name = "Djinn";
                     desc = "An ancient spirit from the middle east. In love with Basilisk. Usually invisible, but is blushing too hard to notice that he's turned red.";
                     break;
                     
            case 7:  name = "Kumiho";
                     desc = "A long-lived fox spirit capable of shapeshifting into various forms, usually of alluring women. Sick of being confused for a kitsune";
                     break;
                     
            case 8:  name = "Centaur";
                     desc = "A creature with the torso of a human and the lower half of a horse. Minotaur is his drinking buddy.";
                     break;
                     
            case 9:  name = "Rabid Wolf";
                     desc = "A normal wolf driven mad by rabies. Extremely dangerous, so beware";
                     break;
                     
            case 10: name = "Basilisk";
                     desc = "The Queen of Snakes. Can't look into mirrors so she thinks she's ugly and therefore unloved. Has a secret admirer... ";
                     break;
                     
            case 11: name = "Minotaur";
                     desc = "A creature with the body of a man and the head of a bull. Really likes pita bread. Can't hold his alcohol.";
                     break;
                     
            case 12: name = "Dragon";
                     desc = "A legendary beast who once destroyed entire kingdoms in mere hours. Spends most of his time doing crossword puzzles and eating pizza.";
                     break;
        }
    }
    
    public boolean getAlive()
    {
        return alive;
    }
    public int getAtk()
    {
       return atk;
    }
    public int getDef()
    {
       return def;
    }
    public int getHp()
    {
       return hp;
    }
    public int getSpd()
    {
       return spd;
    }
    public int getLuck()
    {
       return luck;
    }
    public String getName()
    {
        return name;
    }
    public String getDesc()
    {
        return desc;
    }
    
    public void setLv(int lv)
    {
        level = lv;
    }
    public void setXp(int x)
    {
       xp = x;
    }
    public void setAtk(int a)
    {
        atk = a;
    }
    public void setDef(int d)
    {
        def = d;
    }
    public void setHp(int h)
    {
        hp = h;
        if (hp <= 0)
        {
            death();
        }
    }
    public void setSpd(int s)
    {
        spd = s;
    }
    public void setLuck(int l)
    {
        luck = l;
    }
    //////////////////////////////////////////////////////////////////////////
    
    
    public void death()
    {
        alive = false;
    }
    public int getXp()
    {
        return xp;
    }
    public void killCheat()
    {
        alive = false;
    }
    
    
}
////////////////////////
import java.util.Random;
import java.util.Scanner;
import java.util.*;  
/**
 * Write a description of class Main here.
 *
 * @author (your name)
 * @version (a version number or a date)
 */
public class Main
{
    /**
     * Constructor for objects of class Main
     */
    public static void main(String [] args)
 
    {
        boolean dragonDead = false;
        int atk;
        int def;
        int gold;
        int hp;
        int spd;
        int luck;
        int r;
        int l;
        Scanner sc = new Scanner(System.in);
        Random rand = new Random();
        ArrayList<Item> items = new ArrayList<Item>();
        Player one = new Player(1, 1, 1, 1);
        System.out.println("What a beautiful morning! As an adventurer, your work is very tiring. And what better way to start off the morning than with a good Cici's pizza?"); 
        System.out.println("The waiter sets down the pizza and says \" Enjoy your meal!\". You take a BIG bite. But what's this?");
        System.out.println("All that ended up in your mouth was air! Where did your pizza go? As you glance around, you spy a dragon in a sky...holding your pizza! You must get it back!");
        while (dragonDead == false)
        {
            System.out.println("What is your next course of action? Type \"inn\", \"examine\", \"eat\", \"woods\", or \"dragon\"."); 
            System.out.println("Return to inn to rest for a cost, examine your stats and inventory, eat some food, wander the woods for monsters to fight, or journey onwards to the dragon");
            switch (sc.nextLine())
            {
                case "inn":
                if (one.getGold() >= (2*one.getLv()))
                {
                    System.out.println("You rested for a bit an recovered all your hp!");
                    one.setGold(one.getGold()-(2*one.getLv()));
                    one.setHp(10*one.getLv());
                    System.out.println("You now have "+one.getGold()+" gold!");
                    System.out.println();
                }
                else 
                {
                    System.out.println("Sorry, you don't have enough gold.");
                    System.out.println();
                }
                break;
                /////////////////////////////////////////////////////////////////////////
                
                case "examine":
                System.out.println("Level: "+ one.getLv());
                System.out.println("Hp: "+ one.getHp());
                System.out.println("Atk: "+ one.getAtk());
                System.out.println("Def: "+ one.getDef());
                System.out.println("Spd: "+ one.getSpd());
                System.out.println("Luck: "+ one.getLuck());
                System.out.println("Gold: "+ one.getGold());
                if (items.get(0) != null)
                {
                    for (int i = 0; i < items.size()-1; i++)
                    {
                        System.out.println(items.get(i).getName());
                        System.out.println(items.get(i).getDesc());
                        System.out.println(items.get(i).getStats());
                        System.out.println();
                    }
                }
                else
                {
                    System.out.println("No items in your inventory");
                    System.out.println();
                }
                break;
                //////////////////////////////////////////////////////////////////////////
                
                case "eat":
                if (items.get(0) != null)
                {
                    for (int i = 0; i < items.size()-1; i++)
                    {
                        System.out.println(items.get(i).getName());
                        System.out.println(items.get(i).getDesc());
                        System.out.println(items.get(i).getStats());
                        System.out.println();
                    }
                    System.out.println("If you wish to consume an item to recover your hp(no other stat can be increased at this time), type the corresponding number. If you don't want to eat anything, please enter 0.");
                    if (Integer.parseInt(sc.nextLine())-1 == -1)
                    {
                        break;
                    }
                    else if (items.get(Integer.parseInt(sc.nextLine())-1) == null)
                    {
                        System.out.println("Not an applicable item number");
                        System.out.println();
                        break;
                    }
                    else
                    {
                        one.eat(items.get(Integer.parseInt(sc.nextLine())-1));
                        System.out.println();
                    }
                }
                else
                {
                    System.out.println("No items in your inventory");
                    System.out.println();
                }
                break;
                ///////////////////////////////////////////////////////////////////////
                
                case "woods":
                r = rand.nextInt(9) + 1;
                l = rand.nextInt((one.getLv()+2) + one.getLv());
                Enemy a = new Enemy(r , l);
                System.out.println("You wander the woods, and a monster appears!");
                System.out.println("You have encountered a "+a.getName());
                System.out.println(a.getDesc());
                while (one.getAlive() == true && a.getAlive() == true)
                {
                    if (one.getSpd() >= a.getSpd())
                    {
                        
                    }
                }
                
                case "dragon":
                
                case "levelCheat":
                System.out.println("Input a value");
                one.levelCheat((Integer.parseInt(sc.nextLine())));
                break;
                /////////////////////////////////////////////////////////////////////////
                
                case "winCheat":
                dragonDead = true;
                break;
                /////////////////////////////////////////////////////////////////////////
                
                default: 
                System.out.println("That is not an option!");
                System.out.println();
                break;
            }
        }
        System.out.println("You have defeated the dragon and gotten your precious pizza! Unfortunately it's cold now...and quite stale...and it's not even your pizza!");
        System.out.println("Where's your pizza? NOBODY KNOWS. I BLAME THE MARTIANS AND LIZARD PEOPLE IN THE WHITE HOUSE!");
        
    }
    
}
