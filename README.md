# 🔧 Verilog-A NPN BJT Model for Cadence Virtuoso

This repository contains a simple Verilog-A implementation of an **NPN bipolar junction transistor (BJT)** model operating in the **forward-active region**. The model is designed for use with **Cadence Virtuoso** and **ADE simulation environment**.

---

## 📁 Files Included

- `npn_bjt.va` – Verilog-A code of the NPN transistor model
- `README.md` – This documentation file

---

## 🧪 Features of the Model

This model implements:

- Exponential collector current:
  \[
  I_C = I_S \cdot (e^{V_{BE} / V_T} - 1)
  \]
- Base current:
  \[
  I_B = \frac{I_C}{\beta_F}
  \]
- Emitter current:
  \[
  I_E = - (I_C + I_B)
  \]

### Parameters

| Name   | Description               | Default     |
|--------|---------------------------|-------------|
| `Is`   | Saturation current        | `1e-16 A`   |
| `betaF`| Forward current gain      | `100`       |
| `Vt`   | Thermal voltage           | `0.0259 V`  |

---

## 🛠️ How to Use in Cadence Virtuoso

### 1. Create a Verilog-A Cell View

1. Open **Virtuoso Library Manager**
2. Create a new **Cell View**:
   - **View Name**: `veriloga`
   - **Tool**: `Verilog-A`
3. Paste the code from `npn_bjt.va` and click **Check and Save**

---

### 2. Create a Symbol

1. From the Verilog-A view, go to:
   - `Create` → `Cellview` → `From Cellview`
2. Generate a symbol for your transistor

---

### 3. Use in Schematic

1. Open your testbench schematic
2. Place the NPN transistor symbol
3. Connect terminals and add stimulus (e.g. voltage sources)

![npn](https://github.com/user-attachments/assets/6c401cba-8ef4-4ba1-82cd-7bfb77319c8f)

---

### 4. Setup ADE Simulation

1. Open ADE (e.g., **ADE L / XL / Explorer**)
2. Set up your testbench configuration
3. Choose `Spectre` as the simulator
4. Run the simulation

---

## 📊 Example Use Case

Simulate the I-V characteristics of the BJT by sweeping `V_BE` and measuring `I_C`.

![npn](https://github.com/user-attachments/assets/2e291701-c647-4f78-a8fc-ebf23dc4b5c2)


---

## 🤝 Contributions

Feel free to fork the project, open issues, or submit pull requests if you'd like to contribute or improve the model.

---

## 📜 License

This project is open-source and licensed under the [MIT License](LICENSE).

---

## 🔗 References

- [Verilog-A Language Reference Manual](https://accellera.org/downloads/standards/verilog-a)
- [BJT Theory – Wikipedia](https://en.wikipedia.org/wiki/Bipolar_junction_transistor)

