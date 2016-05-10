#include<iostream>
#include<cmath> //需要用到abs函数

using namespace std;

class CFraction   //类的声明
{
public:

	CFraction(int num=1, int demon=1);     //cons
	~CFraction();     //destroy 

	void show();
	void simplification();
	int GetNum() const;
	int GetDemon() const;   //const成员函数，这样的函数叫常成员函数。
	float GetValue() const; 
	//常成员函数可以理解为是一个“只读”函数，它既不能更改数据成员的值，也不能调用那些能引起数据成员值变化的成员函数，只能调用const成员函数。
	friend const CFraction operator+(const CFraction& lFra,const CFraction& rFra);
	friend const CFraction operator-(const CFraction& lFra,const CFraction& rFra);
	friend const CFraction operator*(const CFraction& lFra,const CFraction& rFra);
	friend const CFraction operator/(const CFraction& lFra,const CFraction& rFra);


	friend bool operator>(const CFraction& lFra,const CFraction& rFra);
	friend bool operator<(const CFraction& lFra,const CFraction& rFra);
	friend bool operator==(const CFraction& lFra,const CFraction& rFra);


private:
	int numerator;
	int demonrator;
	int symbol;   // 0,1 ,2 for negative 


};    //should have a semicolon when a class is defined;

CFraction::CFraction(int num, int demon):symbol(1){          //  函数实现
/*	if(demon==0)
		cout<<"分母不能为0"<<endl;*/
	while(demon==0){
		cout<<"分母不能为0"<<'\n'<<"请重新输入分母"<<endl;
		cin>>demon;
	}
	numerator=abs(num);
	demonrator=abs(demon);
	if(num*demon<0) {
		symbol=2;
		numerator=-numerator;
	}
	if(numerator==0) symbol=0;
	this->simplification();
}

CFraction::~CFraction(){}

int CFraction::GetNum() const{
	return numerator;
}

int CFraction::GetDemon() const{
	return demonrator;
}

float CFraction::GetValue() const{
	return numerator/demonrator;
}

void CFraction::simplification(){
	if(numerator==0) return;
	int a=GCD(abs(numerator),demonrator);
	this->demonrator=demonrator/a;
	this->numerator=numerator/a;

}


void CFraction::show(){
	if(symbol==0){
		cout<<0<<endl;
		return;
	}
	if(numerator!=1)
		cout<<numerator<<"/"<<demonrator<<'\n';
	else
		cout<<numerator<<endl;
}


const CFraction operator+(const CFraction & lFra,const CFraction & rFra){

	return CFraction(lFra.GetNum()*rFra.GetDemon()+lFra.GetDemon()*rFra.GetNum(),lFra.GetDemon()*rFra.GetDemon()); 
	//因为形参为const类型，所以只能调用const类型的成员函数
	//常量对象不能调用非常量成员函数
	//非常量对象可以调用常量成员函数
}

const CFraction operator-(const CFraction& lFra,const CFraction& rFra){
	return CFraction(lFra.GetNum()*rFra.GetDemon()-lFra.GetDemon()*rFra.GetNum(),lFra.GetDemon()*rFra.GetDemon());
}

const CFraction operator*(const CFraction& lFra,const CFraction& rFra){
	return CFraction(lFra.GetNum()*rFra.GetNum(),lFra.GetDemon()*rFra.GetDemon());
}

const CFraction operator/(const CFraction& lFra,const CFraction& rFra){
	return CFraction(lFra.GetNum()*rFra.GetDemon(),lFra.GetDemon()*rFra.GetNum());
}


bool operator>(const CFraction& lFra,const CFraction& rFra){
	if((lFra.GetValue()-rFra.GetValue())>0)
		return true;
	else
		return false;
}

bool operator<(const CFraction& lFra,const CFraction& rFra){
	if((lFra.GetValue()-rFra.GetValue())<0)
		return true;
	else
		return false;
}

bool operator==(const CFraction& lFra,const CFraction& rFra){
	if((lFra.GetValue()-rFra.GetValue())==0)
		return true;
	else
		return false;
}
