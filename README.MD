**��Ҫ��ϸ��freeModbus����ģʽ����ֲ�����ȣ����Է���������ַ**
**freeModbus��Ӧ����ַ��**<https://www.embedded-solutions.at/en/freemodbus/>

**�����̵�����оƬ��STM32F103ZET6,��UCOSII����������ֲ��freeModbus��**
**������ӵ���Ĺ����п���USART�ӿڲ�̫һ�£���Ҫ��PORT.h�ļ����޸ġ�**

**�޸�Ϊ����Ҫ��usart��timer����**��**portserial.c��porttimer.c�޸�Դ�롣**

```c
//��ʼ��freemodbus ����RTUģʽ��ID��
eStatus = eMBInit(MB_RTU, 0x0A,2, 38400, MB_PAR_NONE);
if (MB_ENOERR != eStatus)
{
	printf("freemodbus ����RTU��ģʽʧ��\r\n");
      return false;
}
```

```c
 /* ����Э��ջ�Լ����ںͶ�ʱ�����ѡ�*/ 
 eStatus = eMBEnable();
 if (MB_ENOERR != eStatus)
 {
	printf("ʹ��ModbusProtocolStackʧ��\r\n");
      return false;
 }
```

**��һ��ʱ�����������溯��������5ms����һ�Ρ�**

```c
//һ��ʱ��������ѵ����
 eMBPoll();
```
