Improve [JAVA ACTR](http://cog.cs.drexel.edu/act-r/index.php) by [Dario Salvucci](https://www.cs.drexel.edu/~salvucci/index.php)

task 1: add line

(chunk-type (line (:include visual-object)) end1-x end1-y end2-x end2-y)


```
public class TaskLine extends JPanel implements TaskComponent
{
	/**
	 * Creates a new line.
	 * @param x the x coordinate
	 * @param y the y coordinate
	 * @param width the width
	 * @param height the height
	 * @param color the color of the line
	 */
	public TaskLine (int x, int y, int width, int height, Color color) 
	{
		super();
		setForeground (color);
		setBounds (x, y, width, height);
	}
	
	/**
	 * Creates a new line with the default color (black).
	 * @param x the x coordinate
	 * @param y the y coordinate
	 * @param width the width
	 * @param height the height
	 */
	public TaskLine (int x, int y, int width, int height) 
	{
		this (x, y, width, height, Color.black);
	}
	
	/**
	 * Gets the kind of component (i.e., the "kind" slot of the ACT-R visual object).
	 * @return the kind string
	 */
	public String getKind () { return "line"; }

	/**
	 * Gets the value of component (i.e., the "value" slot of the ACT-R visual object).
	 * @return the value string
	 */
	public String getValue () { return "line"; }
	
	/**
	 * Sets the width of the line.
	 * @param width the new width
	 */
	public void setWidth (int width)
	{
		setBounds (getX(), getY(), width, getHeight());
	}
	
	/**
	 * Changes the width by the given amount.
	 * @param dwidth the change in width
	 */
	public void changeWidth (int dwidth)
	{
		setBounds (getX(), getY(), dwidth+getWidth(), getHeight());
	}
	
	/**
	 * Sets the height of the line.
	 * @param height the new height
	 */
	public void setHeight (int height)
	{
		setBounds (getX(), getY(), getWidth(), height);
	}
	
	/**
	 * Changes the height by the given amount.
	 * @param dheight the change in height
	 */
	public void changeHeight (int dheight)
	{
		setBounds (getX(), getY(), getWidth(), dheight+getHeight());
	}
	
	protected void paintComponent (Graphics g)
	{
		g.setColor (this.getForeground());
		g.fillRect (0, 0, getWidth(), getHeight());
	}
}
```

VisualObject Defintion
``` 
VisualObject (Symbol id, Symbol kind, Symbol value, int x, int y, int w, int h, double d)
		{
			this.id = id;
			this.kind = kind;
			this.value = value;
			this.x = x;
			this.y = y;
			this.w = w;
			this.h = h;
			this.d = d;
			attended = false;
			attendedTime = 0;
			creationTime = model.getTime();
			visloc = null;
		}
```
