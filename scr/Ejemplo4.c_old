#include "so.h"
#include "ciaak.h" //kernel de la ciaa

#define EDU_CIAA_NXP_LED3_VEDE 		0x20
#define EDU_CIAA_NXP_LED2_ROJO 		0x10
#define EDU_CIAA_NXP_LED1_AMARILLO 	0x08

#define EDU_CIAA_NXP_RGB_VEDE		0x04
#define EDU_CIAA_NXP_RGB_AZUL		0x02
#define EDU_CIAA_NXP_RGB_ROJO 	0x01

/*==================[internal data declaration]==============================*/
static int32_t fd_out;
/*==================[internal functions declaration]=========================*/

/*==================[internal data definition]===============================*/

/*==================[external data definition]===============================*/

/*==================[internal functions definition]==========================*/

/*==================[external functions definition]==========================*/
int main(void)
{
	StartOS(AppMode1);
   return 0;
}

/** @} doxygen end group definition */
/** @} doxygen end group definition */
/*==================[end of file]============================================*/

TASK(InitTask){
	ciaak_start();
	 fd_out = ciaaPOSIX_open("/dev/dio/out/0", O_RDWR);
	TerminateTask();
}

TASK(TareaA){
	 uint8 outputs;
    ciaaPOSIX_read(fd_out, &outputs, 1);
    outputs ^= EDU_CIAA_NXP_LED1_AMARILLO;
    ciaaPOSIX_write(fd_out, &outputs, 1);
	TerminateTask();
}
