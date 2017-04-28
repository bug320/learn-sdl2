# 文件：SDL_rect.h
&nbsp;&nbsp;&nbsp;&nbsp;
 > Header file for SDL_rect definition and management functions. 
 
  &nbsp;&nbsp;&nbsp;&nbsp; SDL_Rect 定义和处理函数 的头文件。
 
 > The structure that defines a point
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp;SDL_EnclosePoints
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp;SDL_PointInRect

&nbsp;&nbsp;&nbsp;&nbsp; 定义点的结构体。相关函数：

 * SDL_EnclosePoints
 * SDL_PointInRect

	
		typedef struct SDL_Point
		{
	    	   int x;
	     	   int y;
		} SDL_Point;

 > A rectangle, with the origin at the upper left.
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp; SDL_RectEmpty
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp; SDL_RectEquals
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp; SDL_HasIntersection
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp; SDL_IntersectRect
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp; SDL_UnionRect
 > 
 > &nbsp;&nbsp;&nbsp;&nbsp; SDL_IntersectRectAndLine （注：原文是 SDL_EnclosePoints 觉得应该改成这个）
  &nbsp;&nbsp;&nbsp;&nbsp;一个矩形，原点在左上角。相关函数：
 
 * SDL_RectEmpty
 * SDL_RectEquals
 * SDL_HasIntersection
 * SDL_IntersectRect
 * SDL_UnionRect
 * SDL_IntersectRectAndLine


 		typedef struct SDL_Rect
		{
    		  int x, y;
    		  int w, h;
		} SDL_Rect;
 

## 和 SDL_Point 相关的函数：

 * SDL_EnclosePoints
  原型：
	

		extern DECLSPEC SDL_bool SDLCALL SDL_EnclosePoints(const SDL_Point * points,
                                                   int count,
                                                   const SDL_Rect * clip,
                                                   SDL_Rect * result);
 
  概述：
 > Calculate a minimal rectangle enclosing a set of points
 > 
 > return SDL_TRUE if any points were within the clipping rect

 &nbsp;&nbsp;&nbsp;&nbsp; （在clip矩形内，）计算封闭一组点的最小的矩形。


 &nbsp;&nbsp;&nbsp;&nbsp; 如果任何一个点都在这个 clip 矩形内 ，返回 `SDL_TRUE` 

  参数：

  解释：

  用例：


 * SDL_PointInRect

  原型：

		SDL_FORCE_INLINE SDL_bool SDL_PointInRect(const SDL_Point *p, const SDL_Rect *r)；
   
  概述：
 	 
 > Returns true if point resides inside a rectangle.

 如果点在矩形内 。返回 `SDL_TRUE`。 
  
  参数：

  解释：

  用例：


## 和 SDL_Rect 相关的函数：

 * SDL_RectEmpty

  原型：

  	SDL_FORCE_INLINE SDL_bool SDL_RectEmpty(const SDL_Rect *r)   

  概述：

  >  Returns true if the rectangle has no area.

   如果 矩形没有面积，返回值为 真（`SDL_TRUE`）


  参数：

  解释：

  用例：
 

 * SDL_RectEquals
  原型：

	  	SDL_FORCE_INLINE SDL_bool SDL_RectEquals(const SDL_Rect *a, const SDL_Rect *b)

   
  概述：

  >   Returns true if the two rectangles are equal.
   
  如果两个矩形相等，返回值为真(`SDL_TRUE`)
  

  参数：

  解释：

  用例：


 * SDL_HasIntersection

  原型：
  
  	extern DECLSPEC SDL_bool SDLCALL SDL_HasIntersection(const SDL_Rect * A,
						                                const SDL_Rect * B);

   
  概述：

   >  Determine whether two rectangles intersect.
 
   > SDL_TRUE if there is an intersection, SDL_FALSE otherwise.
 
 
  判断两个矩形是否相交。如果相交，返回 `SDL_TRUE` ，否则返回 `SDL_FALSE`.

 
 

  参数：

  解释：

  用例：


 * SDL_IntersectRect

  原型：

  	extern DECLSPEC SDL_bool SDLCALL SDL_IntersectRect(const SDL_Rect * A,
                                                       const SDL_Rect * B,
                                                       SDL_Rect * result);
   
  概述：
   
 
 >  Calculate the intersection of two rectangles.
 >
 >  SDL_TRUE if there is an intersection, SDL_FALSE otherwise.

 计算两个矩形的相交的部分。如果相交，返回 `SDL_TRUE` ，否则返回 `SDL_FALSE`.


  参数：

  解释：

  用例：


 * SDL_UnionRect

  原型：

  	extern DECLSPEC void SDLCALL SDL_UnionRect(const SDL_Rect * A,
                                               const SDL_Rect * B,
                                               SDL_Rect * result);

   
  概述：
  
 > Calculate the union of two rectangles.

 计算两个矩形的联合

  参数：

  解释：

  用例：

* SDL_IntersectRectAndLine

  原型 ：

  	extern DECLSPEC SDL_bool SDLCALL SDL_IntersectRectAndLine(const SDL_Rect *
                                                              rect, int *X1,
                                                              int *Y1, int *X2,
                                                              int *Y2);

  概述:

 > Calculate the intersection of a rectangle and line segment.
 > 
 >  SDL_TRUE if there is an intersection, SDL_FALSE otherwise.

 计算

  参数: 计算一个矩形和直线段的相交。如果相交，返回 `SDL_TRUE` ，否则返回 `SDL_FALSE`.

  解释:

  用例;