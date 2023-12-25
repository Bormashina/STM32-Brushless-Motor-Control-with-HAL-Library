# STM32-Brushless-Motor-Control-with-HAL-Library
Use the STM32Cube HAL library to control a brushless motor.
#include "stm32f1xx_hal.h"

TIM_HandleTypeDef htim1;
#define MOTOR_PIN TIM_CHANNEL_1

void SystemClock_Config(void);
static void MX_GPIO_Init(void);
static void MX_TIM1_Init(void);

int main(void) {
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();
    MX_TIM1_Init();

    HAL_TIM_PWM_Start(&htim1, MOTOR_PIN);

    while (1) {
        // Motor control logic here
    }
}

void HAL_TIM_MspPostInit(TIM_HandleTypeDef *htim);
