![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/test/badge.svg) ![](../../workflows/fpga/badge.svg)

# ChipDiscover Verilog Example — Elevator

This project is an **example** of a Tiny Tapeout Verilog design for the [ChipDiscover FPGA dev board](https://chipfoundry.io/). It was created from the [chipdiscover-template](https://github.com/chipfoundry/chipdiscover-template) and shows how to wire up a design, fill in [info.yaml](info.yaml), run tests, and build a bitstream.

- [Project documentation](docs/info.md)

## What it does

**Elevator** — A small state machine that simulates an elevator moving between floors. You press a floor button (inputs); the design moves up or down with a delay between floors, shows the current floor on the 7‑segment display, and uses one LED to indicate idle (door open).

- **Inputs** `ui_in[7:0]`: floor buttons (e.g. floor 1–8); DIP switch closed = logic high.
- **Outputs** `uo_out[6:0]`: 7‑segment display (current floor); `uo_out[7]`: idle indicator.

## How to test

- **Simulation:** See [test/README.md](test/README.md). Run the cocotb tests (e.g. `make` in `test/`).
- **FPGA:** Push to the repo; the GitHub Actions workflow builds the bitstream. Download the `fpga_bitstream` artifact, copy `tt_fpga.uf2` to the board’s **FPGAUPDATE** drive. On the board, use the DIP switch to select a floor; the 7‑segment display shows the current floor.

## Create your own project

Use the **[chipdiscover-template](https://github.com/chipfoundry/chipdiscover-template)** to start a new ChipDiscover FPGA project. The template README walks through: creating a repo from the template, editing [info.yaml](info.yaml), adding Verilog in `src/`, and running the FPGA workflow.

## What is Tiny Tapeout?

Tiny Tapeout is an educational project that aims to make it easier and cheaper to get your digital and analog designs manufactured on a real chip. See https://tinytapeout.com.

## Resources

- [FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community](https://tinytapeout.com/discord)
- [Build your design locally](https://www.tinytapeout.com/guides/local-hardening/)
