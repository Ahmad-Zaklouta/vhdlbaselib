GHDL=ghdl
WORK=vhdlbaselib
#WORKDIR=work
GHDLFLAGS=--work=$(WORK) --ieee=synopsys --workdir=$(WORKDIR)

#$@ Contains the target file name.
#$< Contains the first dependency file name.

# list of execs 
#TARGET = dword_filler_tb

# sources from CWD and additional from parent dir
#SOURCES = $(wildcard *.vhd)

# Pbjects is sources with o
# OBJECTS = $(SOURCES:.vhd=.o)
OBJECTS = $(addprefix $(WORKDIR), axi_lite_st_bridge.o\
wb_master_axis_master_bridge.o wb_master_axis_slave_bridge.o\
wb_slave_axis_master_bridge.o)
all: $(OBJECTS)

### Main target
#$(TARGET): $(WORKDIR) $(DEPS) $(OBJECTS)
##	$(CC) $(filter-out $(TARGET:=.o), $(OBJECTS)) $@.o -o $@
#	$(GHDL) -e $(GHDLFLAGS) $@

### To obtain object files
#%.o: %.c $(DEPS)
#	$(CC) -c -o $@ $< $(CFLAGS)
$(WORKDIR)%.o: %.vhd
	$(GHDL) -a $(GHDLFLAGS) $<	
	
# create workdir	
#$(WORKDIR):
#	mkdir $@
#	
## compile hdl lib pckages into workidr
#hdl_lib_pkg:
#	make -C $(PKG_DIR) WORKDIR=$(PKG_WORK_DIR)
	
# To remove generated files
clean:
	#make -C $(PKG_DIR) clean WORKDIR=$(PKG_WORK_DIR)
	rm -rf $(TARGET) $(OBJECTS) $(WORKDIR) *.cf

