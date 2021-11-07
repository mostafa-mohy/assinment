# assinment
void main(){
int ptr;
ANSELA= 0XFF;
ANSELC =0;
ANSELB=0;

TRISA=0xFF;
TRISB=0;


UART1_Init(9600);


while(1){
ptr=ADC_Read(1);
if (ptr < 100)
{
PORTB=0b11110000;
Delay_ms(2000);
UART1_Write(ptr);
UART1_Write_Text("your ptr Reading is less than 100");
UART1_Write(13);
UART1_Write(10);



}
else if (ptr > 140){
PORTB=0b00001111;
Delay_ms(2000);

UART1_Write(ptr);

UART1_Write_Text("your ptr Reading is greater than 140");

UART1_Write(13);
UART1_Write(10);
}
}
}
