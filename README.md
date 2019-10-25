# project
Create project
class ogrenci{
int numara;
String isim;
int vize;
int genel;
ogrenci ileri;

public ogrenci(int numara,String isim,int vize,int genel){
this.numara=numara;
this.isim=isim;
this.vize=vize;
this.genel=genel;
ileri=null;
}  
}
class bliste{
public int ortalama;
ogrenci bas;
ogrenci son;
ogrenci tmp,once;
    public bliste(){
bas=null;
son=null;

}   
void basaekle(ogrenci yeni){
   
if(bas==null){
bas=yeni;
son=yeni;
 System.out.println(yeni.numara+"  "+yeni.isim+"  "+yeni.vize+"  "+yeni.genel);
}
else{
yeni.ileri=bas;
bas=yeni;
  System.out.println(yeni.numara+"  "+yeni.isim+"  "+yeni.vize+"  "+yeni.genel); 
}  
}
void sonaekle(ogrenci yeni){
if(son==null){
son=yeni;
bas=yeni;
   // System.out.println(yeni.numara+"  "+yeni.isim+"  "+yeni.vize+"  "+yeni.genel); 
}
else {
son.ileri=yeni;
son=yeni;
System.out.println(yeni.numara+"  "+yeni.isim+"  "+yeni.vize+"  "+yeni.genel); 
}}
void arayaekle(ogrenci yeni,int numara){
if(bas==null ||son==null){
basaekle(yeni);
}
else{
tmp=bas;
while(tmp.numara!=numara){
tmp=tmp.ileri;
if(tmp==null){
sonaekle(yeni);

}

else  {
yeni.ileri=tmp.ileri;
  tmp.ileri=yeni;
}}
}

    System.out.println(yeni.numara+"  "+yeni.isim+"  "+yeni.vize+"  "+yeni.genel); 
tmp.ileri=null;




}

void bassil(){
   ogrenci sonra; 
bas=bas.ileri;
if(bas==null){
son=null;
}
else {
bas.ileri=null;
sonra=bas; 
}
}

void aradansilme(ogrenci sil,int istenilen){
    tmp=bas;
     once=null;
if(bas==null || son==null){
bas=null;
}
else {
while(tmp!=null){
once=tmp;
tmp=tmp.ileri;
if(sil.numara==istenilen){
tmp.ileri=null;

}
else {
      tmp=tmp.ileri;
      tmp=null;
        }
}}}
 void sonsil(){

tmp=bas;
once=null;
while(tmp!=null){
    once=tmp;
tmp=tmp.ileri;
if(once==null){
son=null;
bas=null;
}
else {
once.ileri=null;
son=once;
}
}
}

    void vizesienyuksek(ogrenci re ) {
     tmp=bas;
     
while(tmp!=null){
   
if(re.vize>tmp.vize){
   
    System.out.println("en yksek vize notu  "+re.numara+"  "+re.isim+"  "+re.vize+"  "+re.genel);
    
}
 tmp=tmp.ileri;

//System.out.println("en yksek vize notu  "+re.numara+"  "+re.isim+"  "+re.vize+"  "+re.genel);
//


tmp=null;
    }}

    void tumunugoster(int n){
    tmp=bas;
    while(n!=0 && tmp!=null){ 
       tmp=tmp.ileri;
           n++;
       System.out.println("/n goster   "+tmp.numara+"  "+tmp.isim+"  "+tmp.vize+"  "+tmp.genel);
    }
    tmp=null;
      n=0; 
    
    
     
    
    }
    void orthesabi(ogrenci gelen){
    tmp=bas;
    while(tmp!=null){
    ortalama=(int) (gelen.vize*0.4+gelen.genel*0.6);
     tmp=tmp.ileri;}
        System.out.println("sonuc ortalamalar  ="+ ortalama);
   }
   
      void sondurumgoster(){ 
          tmp=bas; 
         
          while(tmp!=null){
              tmp=tmp.ileri;
       if(ortalama>50 && tmp.genel>50){ 
     System.out.println("gecenleri   goster =  "+tmp.numara+"  "+tmp.isim+"  "+tmp.vize+"  "+tmp.genel);

         }
          
       else  {
         tmp=tmp.ileri; 
      System.out.println("kalanlari  goster=    "+tmp.numara+"  "+tmp.isim+"  "+tmp.vize+"  "+tmp.genel);}
          
          }   
          tmp=null;
       
    
}}
public class TEST {

    public static void main(String[] args) {
       
     bliste b=new bliste();
     bliste b1=new bliste();
     bliste b2=new bliste();
    b.basaekle(new ogrenci(1231,"ali",23,40));
    b.basaekle(new ogrenci(1234,"veli",13,50));
    b.basaekle(new ogrenci(1233,"ahmet",05,90));
    b.basaekle(new ogrenci(1232,"adem",30,95));
   
