# Operator Overloading 

### Question: Write a program to achieve complex number devision.  
Classname:Point2D
Variables: x and y to store real and imaginary parts of each complex number ( you are not allowed to use any more variables in the class definition)   
Constructors: Point2D(double x, double y) : to intialize values to the member function with respect to the objects defined in the main function.   
Point2D operator/ (Point2D p1,const Point2D& p2):overloaded operator to perform complex devision  
int main() :outside the class intialized objects for 2 points and performs complex devision for them. You can ideally represent the points as  different objects and call them in your function you have designed for operator overloading to perform the task.    
print(): within the class definition that outputs the complext number a +bi in (a,b) format. 
Design a function to overload operator (/) so that it acheives the following result: 
![dividing-complex-numbers](https://user-images.githubusercontent.com/103468688/165282538-405057ba-224a-44dc-aafe-4595979cd4ce.png)


### Solution:
```
#include <iostream>
#include<vector>
using namespace std;
class Point2D {
public:
    Point2D() : x(0), y(0) {}
  //  Point2D(double _x, double _y) : x(_x), y(_y) {}
    //Point2D(double x, double y)
    //{
    //    x = x;
    //    y = y;
    //}
    Point2D(double x, double y)
    {
        this->x = x;
        this->y = y;
    }


    void print() const { std::cout << '(' << x << ", " << y << ')'; }

    Point2D& operator+=(const Point2D&);
    Point2D& operator*=(double);

    double x;
    double y;
};


Point2D operator/(Point2D p1, const Point2D& p2) {
    
    Point2D g;
    double n1,n2, d;
    n1 = p1.x * p2.x + p1.y * p2.y;
    n2 = p2.x + p1.y - p1.x * p2.y;
      //  d = p1.x * p2.x + p1.y * p2.y;
       d= p2.x*p2.x+p2.y*p2.y;
       // std::cout << n1 << n2 << d;
           g.x = n1 / d;
           g.y = n2 / d;
           return g;
      
}


int main() {
    double x1, y1, x2, y2;
    cout << "Enter x and y co-ordinates of P1";
    cin >> x1 >> y1;
    cout<< "Enter x and y co-ordinates of P2";
    cin >> x2 >> y2;

    Point2D e1(x1, y1);
    Point2D e2(x2, y2);

    e1.print(); std::cout << std::endl;
    e2.print(); std::cout << std::endl;
    Point2D devision = e1 / e2;
    devision.print(); std::cout << std::endl;

}
```

