# Formula Reference - Quick Lookup

## Electricity Formulas

### Ohm's Law

**V = I × R**

Where:
- **V** = Voltage (Volts)
- **I** = Current (Amperes)
- **R** = Resistance (Ohms)

**Rearranged**:
- **I = V / R** (Current = Voltage ÷ Resistance)
- **R = V / I** (Resistance = Voltage ÷ Current)

### Power

**P = V × I**

Where:
- **P** = Power (Watts)
- **V** = Voltage (Volts)
- **I** = Current (Amperes)

**Also**:
- **P = I² × R** (Power = Current² × Resistance)
- **P = V² / R** (Power = Voltage² ÷ Resistance)

## Common Calculations

### Resistor for LED

**Given**: Power supply voltage (V_supply), LED voltage (V_LED), LED current (I_LED)

**Resistor value**:
```
R = (V_supply - V_LED) / I_LED
```

**Example**: 5V supply, 2V LED, 20mA current
```
R = (5V - 2V) / 0.020A = 150Ω
Use 220Ω (standard value, safer)
```

### Voltage Divider

**Given**: Input voltage (V_in), Two resistors (R1, R2)

**Output voltage**:
```
V_out = V_in × (R2 / (R1 + R2))
```

## Timing Formulas

### RC Time Constant

**τ = R × C**

Where:
- **τ** (tau) = Time constant (seconds)
- **R** = Resistance (Ohms)
- **C** = Capacitance (Farads)

**Time to charge to 63%**: τ  
**Time to charge to 95%**: 3τ  
**Time to charge to 99%**: 5τ

### 555 Timer Frequency (Astable)

**f = 1.44 / ((R1 + 2×R2) × C)**

Where:
- **f** = Frequency (Hz)
- **R1, R2** = Resistors (Ohms)
- **C** = Capacitor (Farads)

## Binary Conversions

### Binary to Decimal

**Method**: Sum powers of 2 for each 1 bit

**Example**: 1011 (binary)
```
1×2³ + 0×2² + 1×2¹ + 1×2⁰
= 8 + 0 + 2 + 1
= 11 (decimal)
```

### Decimal to Binary

**Method**: Repeated division by 2

**Example**: 11 (decimal)
```
11 ÷ 2 = 5 remainder 1
5 ÷ 2 = 2 remainder 1
2 ÷ 2 = 1 remainder 0
1 ÷ 2 = 0 remainder 1
Read remainders backwards: 1011
```

## Common Values

### Resistor Standard Values (E12 series)
- 10, 12, 15, 18, 22, 27, 33, 39, 47, 56, 68, 82
- Then multiply by 10, 100, 1000, etc.

### Capacitor Common Values
- 0.1µF (100nF) - decoupling
- 10µF - timing
- 100µF - power smoothing

### Voltage Levels
- Logic LOW: 0V to 0.8V
- Logic HIGH: 2.0V to 5V
- Our circuits: 5V = HIGH, 0V = LOW

---

*Keep this reference handy during labs!*
