Change added:
added multiplayer
changement in the code:
MyWorld class:
private void prepare()
    {
        addObject(new Choco(), getWidth()/3, getHeight() - 80);
        addObject(new Grii(), getWidth()/2, getHeight() - 80);
    }

Grii class(the hamster, the second player)
------
public class Grii extends Actor
{
    private int cookiesEaten;
    
    /**
     * Act - do whatever the Choco wants to do. This method is called whenever
     * the 'Act' or 'Run' button gets pressed in the environment.
     */
    public void act()
    {
        // Add your action code here.
        moveAround();
        lookForCookie();
    }
    
    public void moveAround()
    {
    if (Greenfoot.isKeyDown("a")) setLocation(getX()-5, getY());
    if (Greenfoot.isKeyDown("d")) setLocation(getX()+5, getY());
    if (Greenfoot.isKeyDown("w")) setLocation(getX(), getY()-5);
    if (Greenfoot.isKeyDown("s")) setLocation(getX(), getY()+5);
    }
    
    public void lookForCookie() 
    {
    if (isTouching(Cookie.class)) {
        removeTouching(Cookie.class);
        cookiesEaten = cookiesEaten + 1;
    }
    }
}
