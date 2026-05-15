# Embedded Engineer — Skill Framework

## Tổng quan
- **Tên role:** Embedded Engineer
- **Level:** Fresher → Junior → Mid → Senior → Lead
- **Mô tả:** Phát triển phần mềm nhúng cho vi điều khiển, vi xử lý và hệ thống IoT. Lập trình firmware, driver, giao tiếp ngoại vi, hệ điều hành thời gian thực (RTOS), và phát triển sản phẩm phần cứng-phần mềm.
- **Tags:** embedded, firmware, iot, microcontroller, rtos, c, cpp, arm, stm32, esp32, linux-embedded

## Kỹ năng theo cấp độ

### Level 1: Fresher/Junior (0-2 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | C/C++ cơ bản | Cú pháp, Con trỏ (Pointer), Bộ nhớ (Stack/Heap), Struct/Union, Bit manipulation, Preprocessor directives, Volatile, Static | 25% | c, cpp, core, pointer |
| 2 | Vi điều khiển cơ bản (Arduino/STM32/ESP32) | GPIO (Input/Output/Pull-up/Pull-down), ADC (Analog Read), PWM, Timer cơ bản, Interrupt cơ bản (EXTI) | 25% | microcontroller, gpio, arduino, stm32, esp32 |
| 3 | Giao tiếp ngoại vi cơ bản | UART (TX/RX, Baud rate), I2C (Master/Slave, Address), SPI (MOSI/MISO/SCK/CS) | 20% | uart, i2c, spi, peripheral |
| 4 | Toolchain & IDE | Keil/IAR/STM32CubeIDE/Arduino IDE/PlatformIO, Compiler (GCC ARM), Linker script cơ bản, Build process (compile → link → binary) | 15% | toolchain, ide, compiler |
| 5 | Debug cơ bản | Serial print debug, LED debug, Logic Analyzer cơ bản (Saleae), Debugger (ST-Link/J-Link) kết nối, Breakpoint cơ bản | 10% | debugging, serial |
| 6 | Git cơ bản | clone, commit, branch, merge, pull request, .gitignore (build artifacts) | 5% | git, version-control |

### Level 2: Junior/Mid (1-4 năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | RTOS (FreeRTOS/Zephyr) | Task/Thread, Scheduler (Preemptive/Cooperative), Queue, Semaphore, Mutex, Inter-task communication, ISR handling, Task prioritization | 25% | rtos, freertos, zephyr, scheduler |
| 2 | Giao tiếp nâng cao | CAN Bus (ID, Frame, Filter, Arbitration), DMA (Direct Memory Access), I2S (Audio), SDIO (SD Card), USB CDC/HID | 20% | can, dma, i2s, usb, interface |
| 3 | Memory Management | Memory map (Flash/RAM), Stack overflow detection, Heap fragmentation, Custom allocator, Memory alignment, Linker script custom | 15% | memory, flash, ram, linker |
| 4 | Bootloader | Bootloader flow (Boot → App), Flash partitioning, Firmware verification (CRC/Checksum), Jump to application, Fail-safe boot | 15% | bootloader, firmware-update, flash |
| 5 | Debugging nâng cao | JTAG/SWD debugging, Hard Fault analysis, Stack trace, Watchdog, Assert, Core dump analysis, Ozone/SEGGER tools | 10% | debugging, jtag, swd, hard-fault |
| 6 | Lập trình low-power | Sleep modes (Sleep/Stop/Standby), Wake-up sources, Power profiling, Low-power MCU selection, Battery life estimation | 10% | low-power, sleep-mode, battery |
| 7 | Testing firmware | Unit test (Unity/CppUTest/Ceedling), Hardware-in-the-loop (HIL), Mock hardware, CI for firmware | 5% | testing, unity, ceedling |

### Level 3: Mid/Senior (3+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Firmware Update OTA | OTA architecture, Delta update, Rollback mechanism, Secure boot, Signed firmware image, Dual-bank flash, A/B partition | 20% | ota, firmware-update, secure-boot |
| 2 | Linux Embedded (Yocto/Buildroot) | Cross-compilation, Device Tree, Kernel config, Root filesystem, Init system (systemd), Package management (opkg) | 20% | linux-embedded, yocto, buildroot, kernel |
| 3 | IoT Protocols | MQTT (QoS, Topic, Persistent session, Will message), CoAP (RESTful, DTLS), BLE (GATT, Service/Characteristic, Advertising), LoRa/LoRaWAN, ZigBee, NB-IoT | 20% | iot, mqtt, coap, ble, lora, zigbee |
| 4 | Lập trình driver | Bare-metal driver, Register-level programming, Datasheet reading, Interrupt handler, DMA-based driver, Clock configuration, Pin mux | 15% | driver, bare-metal, datasheet |
| 5 | Tiêu chuẩn & An toàn | MISRA C (rules, compliance, static analysis), IEC 61508 (SIL levels), Functional safety, FMEA, Coding standards enforcement | 15% | misra, iec61508, safety, compliance |
| 6 | PCB Design cơ bản | Schematic đọc/hiểu, PCB layout review, KiCad/Eagle/Altium cơ bản, Signal integrity cơ bản, EMI/EMC cơ bản, Grounding | 10% | pcb, hardware, schematic |

### Level 4: Senior/Lead (5+ năm)

| # | Kỹ năng | Mô tả | Trọng số | Tags |
|---|---------|-------|----------|------|
| 1 | Kiến trúc hệ thống nhúng | System-level design, MCU/MPU selection, Power budget, Hardware-software co-design, Modular firmware architecture, Scalability, Maintainability | 25% | architecture, system-design, firmware-architecture |
| 2 | Điều hành đội ngũ | Firmware team leadership, Code review culture, Mentoring, Hiring embedded engineers, Cross-team collaboration (HW/ME/Cloud/App), Technical roadmap | 20% | leadership, mentoring, management |
| 3 | Bảo mật nhúng | Secure boot chain, TrustZone/HSM, Secure element (ATECC608), Secure storage, TLS/DTLS, Firmware encryption, Side-channel attack prevention, Secure provisioning | 20% | security, secure-boot, trustzone, encryption |
| 4 | Sản xuất & Triển khai | Factory provisioning, End-of-line testing, Firmware flashing at scale, Manufacturing test firmware, Serial number management, Key injection, Device lifecycle management | 15% | manufacturing, production, provisioning |
| 5 | Chứng nhận & Compliance | FCC/CE/ETSI certification, UL/CSA safety, EMI/EMC testing, RoHS/REACH, Wireless certification (BLE/WiFi), Regulatory submission process | 10% | certification, compliance, fcc, ce |
| 6 | Chiến lược công nghệ | MCU roadmap planning, Vendor selection, Build-vs-buy analysis, Open-source vs proprietary RTOS, Technology migration, IP strategy | 10% | strategy, vendor, technology |

## Câu hỏi phỏng vấn mẫu theo kỹ năng

### C/C++ cho Embedded

#### Basic
- "Phân biệt `volatile` và `const` trong C? Khi nào dùng `volatile` trong embedded?"
- "Con trỏ (pointer) là gì? Pointer arithmetic, function pointer?"
- "Stack vs Heap trong embedded? Khi nào có stack overflow?"
- "Bit manipulation: Set, Clear, Toggle, Check bit trong C?"
- "Preprocessor directives: #define, #ifdef, #pragma? Macro function vs inline function?"
- "Static variable trong hàm và static global khác gì?"

#### Medium
- "Interrupt Service Routine (ISR): Quy tắc viết ISR? Tại sao không nên dùng printf trong ISR?"
- "Memory alignment là gì? Tại sao data structure cần alignment trên ARM?"
- "Function pointer dùng để làm gì trong embedded? Callback, State machine với function pointer?"
- "Endianness (Little-endian vs Big-endian)? Ảnh hưởng đến serial communication thế nào?"
- "Struct padding là gì? Làm sao tránh padding với `__attribute__((packed))`?"
- "Reentrant function là gì? Tại sao quan trọng trong RTOS?"

#### Advanced
- "Implement memory pool allocator cho embedded system không có `malloc`?"
- "C++ cho embedded: Khi nào nên dùng? Những tính năng C++ nào không nên dùng?"
- "Design pattern cho embedded: State machine, Observer, Command pattern?"
- "Làm sao tối ưu code size cho MCU có 32KB Flash?"
- "C++ RAII trong embedded: Dùng class để quản lý GPIO, SPI, Timer?"

### Vi điều khiển (STM32 / ESP32 / ARM Cortex)

#### Basic
- "GPIO Input vs Output? Pull-up vs Pull-down vs Open-drain?"
- "Timer/Counter: Prescaler, Period, PWM duty cycle tính thế nào?"
- "ADC: Resolution, Sampling rate, Reference voltage? Làm sao đọc ADC value?"
- "Clock tree trên STM32: HSI, HSE, PLL, System Clock, APB, AHB?"
- "Interrupt vs Polling? Ưu nhược điểm?"
- "Watchdog Timer (WDT) là gì? Window Watchdog vs Independent Watchdog?"

#### Medium
- "DMA (Direct Memory Access): Tại sao cần DMA? DMA với ADC, UART, SPI?"
- "ARM Cortex-M: NVIC, Vector table, Interrupt priority, Preemption?"
- "Boot sequence của STM32: Từ reset vector đến main()?"
- "FreeRTOS trên STM32: Cách config heap, tick timer, task stack size?"
- "ESP32: Dual-core architecture? Cách gán task cho core cụ thể?"
- "Làm sao debug Hard Fault trên Cortex-M? CFSR, HFSR, stack frame?"

#### Advanced
- "So sánh ARM Cortex-M0/M3/M4/M7? Khi nào chọn MCU nào?"
- "Làm sao implement custom bootloader với dual-bank flash trên STM32?"
- "Tối ưu power consumption: STM32 sleep mode, clock gating, peripheral control?"
- "Cache coherency trên Cortex-M7? Data cache vs Instruction cache?"
- "Làm sao tận dụng FPU và DSP instructions trên Cortex-M4/M7?"

### RTOS (FreeRTOS / Zephyr)

#### Basic
- "RTOS là gì? Khác gì Bare-metal và General-purpose OS (Linux)?"
- "Task/Thread: Tạo task, Task priority, Task state (Ready/Running/Blocked/Suspended)?"
- "FreeRTOS scheduler: Preemptive vs Cooperative? Tickless idle?"
- "Queue trong FreeRTOS: Gửi/nhận data giữa các task?"
- "Semaphore vs Mutex? Binary Semaphore vs Counting Semaphore?"
- "Task notification trong FreeRTOS là gì? Nhanh hơn Queue không?"

#### Medium
- "Deadlock là gì? Làm sao phát hiện và tránh deadlock trong RTOS?"
- "Priority Inversion: Nguyên nhân và cách giải quyết (Priority Inheritance)?"
- "Memory management trong FreeRTOS: heap_1 đến heap_5? Khi nào dùng loại nào?"
- "Software Timer trong FreeRTOS: One-shot vs Auto-reload? Timer task?"
- "Zephyr vs FreeRTOS: Khác biệt chính? Khi nào chọn Zephyr?"
- "Interrupt management trong RTOS: ISR to task communication? Deferred interrupt?"

#### Advanced
- "Làm sao estimate stack size cho mỗi task? Stack high watermark?"
- "Scheduling analysis: Rate Monotonic Scheduling (RMS)? Làm sao chứng minh schedule được?"
- "Multi-core RTOS: SMP vs AMP? Cách schedule task trên multi-core MCU?"
- "Zephyr Device Tree: Cách định nghĩa và sử dụng device tree node?"
- "RTOS porting: Cần làm gì để port FreeRTOS sang MCU mới?"
- "Làm sao đo CPU utilization và task execution time trong RTOS?"

### Giao tiếp & Ngoại vi

#### Basic
- "UART: Baud rate là gì? Start bit, Stop bit, Parity? Làm sao chọn baud rate?"
- "I2C: Master vs Slave, địa chỉ 7-bit vs 10-bit? Clock stretching là gì?"
- "SPI: CPOL, CPHA (4 modes)? Full-duplex vs Half-duplex?"
- "CAN Bus: Arbitration, ID, Standard vs Extended frame?"
- "GPIO interrupt: Rising edge vs Falling edge vs Both? Debouncing là gì?"
- "Pull-up vs Pull-down resistor: Tại sao cần? Giá trị điển hình?"

#### Medium
- "I2C clock stretching: Nguyên nhân và cách xử lý?"
- "SPI multi-slave: Daisy chain vs Independent CS?"
- "CAN Bus: Bit timing (Tseg1, Tseg2, SJW)? Làm sao tính baud rate?"
- "DMA transfer modes: Circular vs Normal? Double buffering?"
- "USB CDC (Virtual COM Port) hoạt động thế nào? USB descriptor?"
- "Làm sao debug I2C/SPI bus với logic analyzer?"
- "RS-485 vs RS-232 vs UART? Khác biệt về điện áp và topology?"

#### Advanced
- "Làm sao implement software I2C khi phần cứng không đủ peripheral?"
- "CANopen vs J1939 vs raw CAN: Khi nào dùng protocol layer nào?"
- "High-speed design: Signal integrity cho SPI clock > 50MHz?"
- "Làm sao implement USB composite device (CDC + HID)?"
- "EMI/EMC considerations cho external communication buses?"

### Bootloader & Firmware Update

#### Basic
- "Bootloader là gì? Tại sao cần bootloader?"
- "Quy trình firmware update cơ bản: Erase → Write → Verify?"
- "Flash memory: Sector/Page, Write alignment, Minimum erase unit?"
- "CRC/Checksum: Dùng để verify firmware integrity thế nào?"
- "Vector table relocation trên ARM Cortex-M: SCB->VTOR?"

#### Medium
- "Dual-bank vs Single-bank Flash? Lợi ích của dual-bank?"
- "A/B partition update strategy: Rollback nếu firmware mới lỗi?"
- "Secure boot: Trust chain, Signature verification, Public key storage?"
- "Delta OTA: Chỉ update phần thay đổi? Kỹ thuật diff/patch cho firmware?"
- "Fail-safe bootloader: Nếu mất điện giữa chừng khi update?"
- "External Flash vs Internal Flash cho firmware update?"

#### Advanced
- "Thiết kế bootloader với encrypted firmware image?"
- "Làm sao implement OTA cho thiết bị có 64KB RAM mà firmware 512KB?"
- "Secure boot từ ROM → Bootloader → Application? Chain of trust?"
- "Firmware update qua BLE? DFU (Device Firmware Update) profile?"
- "Multiple firmware images: Factory image vs Update image vs Recovery image?"

### Linux Embedded (Yocto / Buildroot)

#### Basic
- "Linux Embedded là gì? Khác Linux desktop/server thế nào?"
- "Cross-compilation là gì? Tại sao cần cross-compile?"
- "Device Tree là gì? Tại sao Linux cần device tree?"
- "Kernel module vs Built-in driver? insmod, modprobe, lsmod?"
- "Buildroot vs Yocto: Khác biệt cơ bản?"

#### Medium
- "Yocto: BitBake, Recipe, Layer? Cách tạo custom layer?"
- "Buildroot: Cách add package, config kernel, custom rootfs overlay?"
- "Kernel configuration: menuconfig, defconfig, fragment config?"
- "Init system: systemd vs BusyBox init vs SysV init?"
- "Filesystem choices: ext4 vs squashfs vs UBIFS? Khi nào dùng cái nào?"
- "Device Tree Overlay dùng để làm gì?"

#### Advanced
- "Yocto: Cách tạo custom distro, custom image, SDK?"
- "Kernel debugging: KGDB, JTAG, printk, ftrace?"
- "Boot time optimization: Làm sao boot Linux trong < 1 giây?"
- "Secure boot trên Linux Embedded: U-Boot verified boot, FIT image?"
- "Yocto layer management cho nhiều sản phẩm chia sẻ code?"

### IoT Protocols

#### Basic
- "MQTT: Publish/Subscribe model? Broker, Topic, QoS levels (0/1/2)?"
- "BLE: GAP vs GATT? Advertising, Connection, Service, Characteristic?"
- "CoAP là gì? Khác gì HTTP? Dùng UDP hay TCP?"
- "LoRa vs LoRaWAN: LoRa là lớp vật lý, LoRaWAN là giao thức mạng?"
- "ZigBee: Mesh network? Coordinator, Router, End Device?"
- "WiFi trong IoT: Station mode vs AP mode vs Smart Config?"

#### Medium
- "MQTT: Persistent session, Will message, Retained message, Keep-alive?"
- "BLE: MTU, Connection interval, Slave latency? Ảnh hưởng đến power?"
- "CoAP: Confirmable vs Non-confirmable messages? Observe pattern?"
- "LoRaWAN: OTAA vs ABP? ADR (Adaptive Data Rate)? Duty cycle?"
- "MQTT-SN vs MQTT? Khi nào dùng MQTT-SN?"
- "Làm sao chọn IoT protocol: Range, Data rate, Power, Cost?"

#### Advanced
- "Làm sao implement MQTT bridge cho thiết bị không có TCP/IP?"
- "BLE Mesh vs ZigBee vs Thread: So sánh cho smart home?"
- "DTLS và OSCORE cho CoAP security? So với TLS cho MQTT?"
- "NB-IoT vs LTE-M vs LoRaWAN: So sánh cho IoT quy mô lớn?"
- "Làm sao thiết kế protocol custom cho sensor network tiết kiệm pin?"
- "MQTT 5.0: Có gì mới? Shared subscription, Session expiry?"

### Low-Power & Battery

#### Basic
- "Sleep modes trên MCU: Sleep, Deep Sleep, Stop, Standby khác gì?"
- "Làm sao estimate battery life? Capacity (mAh) / Current consumption?"
- "Wake-up sources: GPIO, RTC, Watchdog, Communication peripheral?"
- "Dynamic voltage scaling và clock gating là gì?"
- "Làm sao đo current consumption của thiết bị IoT?"

#### Medium
- "BLE power optimization: Connection interval, TX power, Advertising interval?"
- "Làm sao chọn battery cho sản phẩm IoT? Li-Po vs Li-Ion vs Alkaline vs CR2032?"
- "Power profiling: Oscilloscope + Current probe? JouleScope? Power analyzer?"
- "Energy harvesting: Solar, Thermal, RF? Khả thi cho loại thiết bị nào?"
- "RTOS tickless idle mode: Lợi ích và cách config trong FreeRTOS?"

#### Advanced
- "Thiết kế firmware cho thiết bị chạy 5 năm với 1 viên pin CR2032?"
- "Dynamic power management: Adaptive sampling rate, Context-aware sleep?"
- "Power gating vs Clock gating: Khác biệt và trade-off?"
- "Làm sao implement power-aware scheduling trong RTOS?"
- "Battery fuel gauge: Coulomb counting vs Voltage-based? Impedance tracking?"

### Testing & Debugging

#### Basic
- "Unit test cho firmware: Unity, CppUTest, Ceedling?"
- "Serial debug: printf debugging? Ưu và nhược?"
- "GPIO toggle để đo timing với oscilloscope?"
- "Assert trong firmware: Dùng assert để làm gì? Release vs Debug?"
- "Watchdog dùng để detect treo hệ thống thế nào?"

#### Medium
- "JTAG/SWD: Cách kết nối, Breakpoint (hardware vs software), Watchpoint?"
- "Hard Fault analyzer: CFSR, HFSR, MMFAR, BFAR registers?"
- "Hardware-in-the-loop (HIL) testing: Setup, Mock sensors, Automated test?"
- "CI/CD cho firmware: GitHub Actions build + test trên target thật?"
- "Làm sao test race condition và deadlock trong RTOS?"

#### Advanced
- "Stress testing firmware: Làm sao test 1000 giờ chạy liên tục?"
- "Test coverage cho firmware: Branch coverage, MC/DC cho safety-critical?"
- "Automated regression testing với hardware test jig?"
- "Làm sao test fail-safe mechanism (mất điện, watchdog reset, corrupted flash)?"
- "Profiling firmware: Execution time, Stack usage, Heap usage per task?"

### Tiêu chuẩn An toàn (MISRA / IEC 61508)

#### Basic
- "MISRA C là gì? Tại sao cần MISRA C?"
- "MISRA C: Rule categories? Mandatory, Required, Advisory?"
- "Static analysis tools: PC-lint, Coverity, SonarQube cho C?"
- "IEC 61508 là gì? SIL 1-4 khác gì?"
- "Coding standards ngoài MISRA: CERT C, BARR-C?"

#### Medium
- "MISRA C:2012 vs MISRA C:2004? Những thay đổi chính?"
- "Làm sao enforce MISRA compliance trong CI pipeline?"
- "Deviation process: Khi nào được phép deviate từ MISRA rule?"
- "FMEA (Failure Mode and Effects Analysis) cho firmware?"
- "SIL decomposition: Làm sao đạt SIL 3 với 2 subsystem SIL 2?"

#### Advanced
- "Làm sao đạt ISO 26262 ASIL-D cho automotive firmware?"
- "IEC 62304 cho medical device software? Khác gì IEC 61508?"
- "Safety manual và safety case: Cấu trúc và nội dung?"
- "Dual-channel architecture với diversity (khác CPU, khác compiler)?"
- "Formal methods trong safety-critical firmware: Model checking, Theorem proving?"

## Dự án mẫu để lấp gap

### Level Junior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Đèn LED điều khiển từ xa qua UART/Bluetooth" | GPIO, UART, PWM, Timer, Interrupt, Serial protocol | 2-3 tuần | STM32 (HAL), UART, HC-05 Bluetooth, LED RGB |
| 2 | "Máy đo nhiệt độ & độ ẩm hiển thị LCD" | I2C (cảm biến), SPI/I2C (LCD), ADC, Sensor reading, Data processing | 2-3 tuần | STM32/ESP32, DHT22/SHT3x, I2C LCD, UART debug |
| 3 | "Hệ thống tưới cây tự động với Arduino" | GPIO, ADC (soil moisture), Relay control, Timer scheduling, Serial monitor | 2 tuần | Arduino, Soil moisture sensor, Relay module, Pump |
| 4 | "Mini Oscilloscope qua Serial Plotter" | ADC sampling, DMA, Timer trigger, Data format, Serial communication tốc độ cao | 3-4 tuần | STM32, ADC + DMA, UART, Python script hiển thị |
| 5 | "Đồng hồ Real-time với RTC và EEPROM" | I2C (RTC + EEPROM), Timer, Interrupt, Power management (backup battery) | 2-3 tuần | STM32, DS3231 RTC, AT24Cxx EEPROM, OLED SSD1306 |

### Level Mid — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Firmware cho thiết bị IoT đo chất lượng không khí" | RTOS, MQTT, WiFi, Sensor fusion (multi-sensor), OTA update, Low-power sleep | 6-8 tuần | ESP32, FreeRTOS, MQTT, PMS5003+SGP30, AWS IoT, OTA |
| 2 | "Bootloader tùy chỉnh với Firmware Update qua UART/CAN" | Bootloader, Flash partitioning, CRC verification, Fail-safe, Communication protocol | 4-6 tuần | STM32, UART/CAN, Custom bootloader, YMODEM protocol |
| 3 | "Hệ thống điều khiển động cơ BLDC" | PWM, ADC current sensing, PID control, Hall sensor/Encoder, Safety shutdown | 6-8 tuần | STM32, Timer (6-step commutation), DRV8301, MOSFET |
| 4 | "Data Logger đa kênh với SD Card" | SPI (SD Card), FATFS, DMA (ADC), Ring buffer, Timestamp, Power-loss protection | 4-6 tuần | STM32, SPI SD Card, ADC+DMA, RTC, FatFS |
| 5 | "BLE Sensor Beacon Mesh Network" | BLE GATT, Advertising, Mesh communication, Low-power optimization, Mobile app interface | 6-8 tuần | nRF52/ESP32, Zephyr BLE, nRF Connect SDK, Mobile companion app |

### Level Senior — Gợi ý dự án

| # | Tên dự án | Lấp kỹ năng | Timeline | Tech stack |
|---|-----------|-------------|----------|------------|
| 1 | "Gateway IoT Linux Embedded đa giao thức" | Linux Embedded (Yocto/Buildroot), Multi-protocol bridge (MQTT↔BLE↔ZigBee↔LoRa), OTA cho gateway và end-device, Security | 12-16 tuần | i.MX/AM62x, Yocto Linux, MQTT broker, BLE/ZigBee/LoRa module, AWS Greengrass |
| 2 | "Firmware cho thiết bị y tế đạt IEC 62304 Class C" | MISRA C, Safety architecture, Dual-channel, Watchdog hierarchy, FMEA, Unit test coverage > 95%, Traceability matrix, Documentation | 16-20 tuần | STM32 (dual MCU), MISRA C, IEC 62304, Ceedling, SIL verification |
| 3 | "Hệ thống điều khiển robot công nghiệp với EtherCAT" | Real-time control, EtherCAT slave, CANopen over EtherCAT (CoE), Motion control, Safety PLC interface, Multi-axis sync | 12-16 tuần | STM32 + ET1100, EtherCAT, CAN, Safety controller, Servo driver |
| 4 | "Secure Firmware Platform cho thiết bị IoT" | Secure boot, TrustZone, Secure storage (ATECC608), Encrypted OTA, Secure provisioning, PKI infrastructure, FOTA server backend | 12-16 tuần | STM32/ESP32 + Secure Element, TrustZone, AWS IoT Core, Custom provisioning tool |
| 5 | "Automotive ECU Firmware đạt ISO 26262 ASIL-B" | AUTOSAR-lite, CAN/LIN, UDS (ISO 14229), DTC management, Safety monitoring (watchdog, voltage, temperature), End-of-line programming | 14-18 tuần | STM32/S32K, CAN, UDS, ISO 26262, Vector tools, ASIL-B compliance |
