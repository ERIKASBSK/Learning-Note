













```c
#include <iostream>
#include <string>
using namespace std;

class GradeBook {                  // class 類別
private:
    string courseName;             // data member 資料成員 / attribute 屬性

public:
    void setCourseName(string name) {   // member function / set 函式
        courseName = name;
    }

    string getCourseName() const {      // member function / get 函式
        return courseName;
    }

    void displayMessage() const {       // member function 成員函式
        cout << "Course: " << courseName << endl;
    }
};

int main() {
    GradeBook myBook;              // object 物件
    string name = "Math";          // variable 變數

    myBook.setCourseName(name);    // 呼叫 set，name 是 argument
    myBook.displayMessage();       // 呼叫函式


    return 0;
}

```
