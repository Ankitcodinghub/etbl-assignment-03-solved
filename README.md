# etbl-assignment-03-solved
**TO GET THIS SOLUTION VISIT:** [ETBL Assignment 03 Solved](https://www.ankitcodinghub.com/product/etbl-electronic-technologies-and-biosensors-laboratory-solved-2/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;127139&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;ETBL Assignment 03 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
Objective

In this Project, you have to setup an I2C Slave using the PSoC and sample 2 analog sensors using a Delta-Sigma ADC. For data visualization, you will use the Bridge Control Panel to plot the two signals.

Connections

Pin | Description | :———–:|————-| 2.1 | Built-in LED 2.5 | Analog Channel 0: Temperature sensor (*) 2.6 | Analog Channel 1: LDR (photoresistor) (**) 12.0 | I2C SCL 12.1 | I2C SDA

(*) See the connection scheme below to hook up the photoresistor (Datasheet)

(**) Please refer to the following image and to the datasheet of the component (TMP36GZ) to hook up the temperature sensor

Requirements

The Project will have to meet the following requirements: – Sample two analog sensors using a single 16-bit Delta-Sigma ADC (hint: you can use the Analog Mux for this) – Each sample (of each channel) has to be the average of 5 consecutive samples buffered opportunely – Set up an I2C Slave (EZI2C) to send the averaged data for the 2 channels to the Bridge Control Panel. Configure the EZI2C component as follows: 100 kbps data rate, 1 address (0x08) – The required transmission data rate is 50 Hz – Set up a Timer with an ISR at the appropriate frequency to guarantee the data transmission rate (50 Hz) of the averaged data (5 samples) – Control the operation of the device writing the value of the Control Register of the I2C slave (refer to the table below) – Set up the I2C Slave buffer of the EZI2C according to the following table (set the WHO AM I to 0xBC) – Turn on the built-in LED when the status is equal to 0b11, and turn it off otherwise (refer to the description of Control Register 1 for more info)

I2C Slave Buffer Structure

Address | Description | R/W | :———–:|—————|:—:| 0x00 | Control Reg 1 | R/W | 0x01 | Control Reg 2 | R/W | 0x02 | Who Am I | R | 0x03 | Ch0 Bit 15-8 | R | 0x04 | Ch0 Bit 07-0 | R | 0x05 | Ch1 Bit 15-8 | R | 0x06 | Ch1 Bit 07-0 | R |

Control Register 0 Description (Address 0x00)

Bit | Description | R/W | Default | :—–:|———————–|:—:|:——-:| 7 | –reserved | – | – | 6 | –reserved | – | – | 5 | Average samples bit 3

| R/W | 0 | 4 | Average samples bit 2 | R/W | 0 | 3 | Average samples bit 1 | R/W | 0 | 2 | Average samples bit 0 | R/W | 0 | 1 | Status bit 1 | R/W |

0 | 0 | Status bit 0 | R/W | 0 |

The status (bits 0 and 1) can be either set to 0b00 (device stopped), 0b01 to sample the first channel (Ch0), 0b10 to sample the second channel (Ch1), and finally 0b11 to sample both channels. The register contains also the number of samples to be used for the computation of the average. Set the value of bits 2-5 of the Control Register 0 to meet the requirements of the project.

Control Register 1 Description (Address 0x00)

Bit | Description | R/W | Default | :—–:|———————–|:—:|:——-:| 7-0 | Timer 1 Period Value | R/W | 0 |

The Control Register 1 contains the 8-bit period value of the Timer used to generate the ISR required to sample the analog channels using the Delta-Sigma ADC. Configure this register to meet the transmission data rate specified for this project.

Setup and Assignment Delivery

One student from the team forks this repository

Each team member clones the forked repository by entering the following command in the terminal:

git clone https://github.com/[your_username]/AY2021_II_HW_03.git – Open up the workspace in PSoC Creator –

Activate the project with your group number – Work on your project – In your Group folder, save the Bridge Control Panel configuration files (GROUP_XX.ini and GROUP_XX.iic) inside BRIDGE_CONTROL_PANEL_CONFIG_FILES folder

Evaluation
