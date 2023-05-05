2.cpp
#include<iostream>

using namespace std;

class matrix
{
	    int **a,i,j,r,c;
public:
	    matrix()           // Dynamic Constructor
	    {
			cout<<"Enter Row and Coloum of Matrix :\n";
			cin>>r>>c;
			a=new int*[r];
			for(i=0; i<r; i++)
			    {
				    a[i]=new int[c];
			    }
	     }
	     void accept()
	     {
			cout<<"Enter elements for matrix:\n";
			for(i=0; i<r; i++)
			{
				for(j=0; j<c; j++)
				    {
					cin>>a[i][j];
				    }
			}
	    }
	    void display()
	     {
			cout<<"Elements of matrix are:\n";
			for(i=0; i<r; i++)
			{
				for(j=0; j<c; j++)
				    {
					cout<<a[i][j]<<"\t";
				    }
				    cout<<endl;
			}
	    }
	    void transpose()
	    {
			cout<<"Transpose of Matrix is :\n";
			for(i=0;i<c;i++)
			{
				for(j=0;j<r;j++)
				{
					cout<<a[j][i]<<"\t";
				}
				cout<<endl;
			}
	    }
};

int main()
{

	matrix obj1;
	obj1.accept();
	obj1.display();
	obj1.transpose();

}


1.cpp
#include<iostream>
using namespace std;

class Square {
    public:
        int s;

        void getdata() {
            cout << "Enter the side of the square: ";
            cin >> s;
        }

        int calArea() {
            return (s*s);
        }

        friend void compare(int s, int r);
};

class Rectangle {
    public:
        int l, w;

        void getdata() {
            cout << "Enter the length of the rectangle: ";
            cin >> l;
            cout << "Enter the width of the rectangle: ";
            cin >> w;
        }

        int calArea() {
            return (l*w);
        }

        friend void compare(int s, int r);
};

void compare(int s, int r) {
    if(s > r) {
        cout << "The area of square is bigger than area of rectangle." << endl;
    } else {
        cout << "The area of rectangle is bigger than area of square." << endl;
    }
}


int main() {
    int s_area, r_area;
    Square s1;
    Rectangle r1;

    s1.getdata();
    s_area = s1.calArea();

    r1.getdata();
    r_area = r1.calArea();

    cout << "Square: " << s_area << endl;
    cout << "Rectangle: " << r_area << endl;

    compare(s_area, r_area);

    return 0;
}

1.node

const http = require('http');
const fs = require('fs');

const server = http.createServer((req, res) => {
  const filePath = '.' + req.url;
  fs.readFile(filePath, (err, data) => {
    if (err) {
      res.writeHead(404, {'Content-Type': 'text/plain'});
      res.write('404 Not Found');
      res.end();
    } else {
      res.writeHead(200, {'Content-Type': 'text/plain'});
      res.write(data);
      res.end();
    }
  });
});

server.listen(3000, () => {
  console.log('Server running on port 3000');
});
  
  
  2.node
  
  var mysql = require('mysql');

var con = mysql.createConnection({

  host: "localhost",

  user: "root",

  password: "root",

  database: "mydb"

});

con.connect(function(err) {

  if (err) throw err;

  con.query("SELECT * FROM customers", function (err, result, fields) {

    if (err) throw err;

    console.log(result);

  });

});



