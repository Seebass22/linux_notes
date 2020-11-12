# syntax check
ghdl -s file.vhd

# compile and create waveform
ghdl -a adder.vhd
ghdl -a tb_adder.vhd
ghdl -e tb_adder
ghdl -r tb_adder --vcd=wave.vcd

# view in GTKWave
gtkwave wave.vcd
