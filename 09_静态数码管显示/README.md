##静态数码管显示
#138译码器使我们只需要P2_2、P2_30、P2_4 三个端口能控制数码管三个端口的亮灭，以真值表的形式来控制八个端口
#74HC245作为双向数据缓冲器
#数码管断码表#unsigned char NixieTable[]={0x3F,0x06,0x5B,0x4F,0x66,0x6D,0x7D,0x07,0x7F,0x6F,0x77,0x7C,0x39,0x5E,0x79,0x71,0x00};
#数码管显示函数

void Nixie(unsigned char Location,Number)
{
	switch(Location)
	{
		case 1:P2_4=1,P2_3=1,P2_2=1;break;
		case 2:P2_4=1,P2_3=1,P2_2=0;break;
		case 3:P2_4=1,P2_3=0,P2_2=1;break;
		case 4:P2_4=1,P2_3=0,P2_2=0;break;
		case 5:P2_4=0,P2_3=1,P2_2=1;break;
		case 6:P2_4=0,P2_3=1,P2_2=0;break;
		case 7:P2_4=0,P2_3=0,P2_2=1;break;
		case 8:P2_4=0,P2_3=0,P2_2=0;break;
		
	}
	P0=NixieTable[Number];
}