#include<avr/io.h>
#include<util/delay.h>
#include<avr/adc.h>
void main()
{
DDRA=0x00;
DDRB=0xFF;
adc_init();

while(1)
{
int x,y;
x=read_adc_channel(1);
y=read_adc_channel(2);

if((310<x)&&(x<333)&&(312<y)&&(y<339))
{
PORTB=0x00;
_delay_ms(200);

}
else if((260<x)&&(x<286)&&(313<y)&&(y<333))
{
PORTB=0x01;
_delay_ms(200);

}
else if((369<x)&&(x<375)&&(309<y)&&(y<339))
{
PORTB=0x08;
_delay_ms(200);

}
 else if((300<x)&&(x<335)&&(364<y)&&(y<384))
{
PORTB=0x09;
_delay_ms(200);

}
else if ((308<x)&&(x<329)&&(260<y)&&(y<280))
{
PORTB=0x06;
_delay_ms(400);
}
}
}
