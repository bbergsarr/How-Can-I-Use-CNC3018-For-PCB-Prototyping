# How Can I Use CNC-3018 Router For PCB Prototyping ?
<p align="center">
<b> ~~~~~~~~~~CARVE THE TRACES OF YOUR MIND INTO COPPER~~~~~~~~~~
</b><br>
<br><br>

# Step By Step PCB Production 

All the steps I have used to made PCB prototyping
  
Step |     Process  | Description / Source    |
|--|--------------|--------------------|
|1   |  Downland Universal G Code Sender (UGS) Program                 | https://winder.github.io/ugs_website/download/
|2   |  Making Adjustments Within The UGS Program                      | Establishing The Connection Between The Computer And The CNC-Router,Adjusting Engraving Environment
|3   |  Hardware Design                                                | Create a Gerber File From Your Design
|4   |  Downland FlatCAM Program                                       | 
|5   |  Single Layer 2D CAM Process                                    | Get the G Code from CAM
|5   |  Preparing The Engraving Environment                            | Get the G Code from CAM
|6   |  Single Layer PCB Prototyping-Reset X,Y Zero And Probbing       | Get the G Code from CAM 
|6   |  Single Layer PCB Prototyping-Surface Mapping                   | Get the G Code from CAM 
|6   |  Single Layer PCB Prototyping-Top Layer Engraving               | Get the G Code from CAM 
|6   |  Single Layer PCB Prototyping-Drilling The Holes                | Get the G Code from CAM 
|6   |  Single Layer PCB Prototyping-Profile Border Cutting            | Get the G Code from CAM
|6   |  Single Layer PCB Prototyping-Profile Border Cutting            | Get the G Code from CAM

# Downland Universal G Code Sender Program
Universal G-code Sender, often abbreviated as UGS, is a cross-platform Java-based program designed to stream G-code to CNC machines, offering an easy interface and real-time control over operations. G-code is the language used to instruct CNC machines how to move, cut, and drill according to a specific design. UGS acts as a bridge between your computer and your CNC machine, ensuring that the machine follows your commands accurately.

->UGS works with a variety of CNC machines and is compatible with several hardware controllers, including GRBL, TinyG, and Smoothieboard.

->UGS's dashboard provides essential information such as job progress, spindle speed, and machine coordinates, making it easy to monitor and control your CNC machine.

->UGS is its ability to control CNC machines in real-time. You can pause, stop, or adjust the machine's actions as needed. This is particularly useful when running long or complex operations where unexpected issues may arise, requiring on-the-fly adjustments.

->UGS is its 3D G-code visualization tool, which provides a graphical representation of the toolpath before it is sent to the CNC machine. This feature is invaluable in catching potential mistakes in the G-code or previewing how the machine will move. You can zoom in, rotate, and analyze the toolpath in detail, ensuring that the operations will go smoothly.

->UGS supports precise machine positioning using its built-in jogging controls. Whether you’re setting the origin point or moving the machine to specific coordinates, UGS offers smooth and precise control. Additionally, for CNC machines with probing capabilities, UGS supports probing commands, enabling automated measurement and alignment also by using UGS AutoLeveler you can create surface map for precise manufacturing.

<b> After a short theoretical introduction, let's start the program;
</b><br>

# Making Adjustments Within The UGS Program 
<p align="center">
<img src="UGS.png" width="700"/>

<p align="center">
<b> Fig.1 Interface of UGS Program
</b><br>

In the UGS program, which we will use all its features later,Now all we need to do is establish the connection between the computer and the CNC router and after this connection, move the spindle to a suitable region and height with some jogging maneuvers.

For Connections;

Note:In CNC control card,making sure that you connect the power,USB port and open the switch before these steps;

1-Firmware - GRBL

2-Port - Choose True Port Between CNC Router and PC.

3-Baud - Choose Proper Baud Between CNC Router and PC. (Recommended Value is 115200 bit/sec)

4-After Making Sure These Parameters,You Can Connect CNC Router and PC By Clicking Conncetion Icon.

For Jogging;

Thanks to the controller located at the bottom left of the program and based on Cartesian axes, the spindle is easily pulled into the appropriate area.
Also we have an adjustment area for how far to go with each click, on the XY and Z axes separately (Step Size).


# Hardware Design 

In this area, instead of providing basic hardware design information, I will talk about important design parameters for CNC-Router.

1-Track Width:

During design, one of the main parameters is the thickness of our roads. This thickness is determined to be suitable for certain purposes and the electric current that will pass.

This value is really important when using a CNC Router. In addition to the theoretically appropriate thickness you have found, it is recommended to give a value around 30% higher due to some additional parameters and unintentional errors.

2-DRC Parameters:

2a-(Wire-Pad-Via) Clearance

The distance between these elements(Wire-Pad-Via), which serve as carriers of different signals, is perhaps the most important parameter in the production phase. Here, depending on the adequacy of the machine and the possibility of errors, it is recommended to give a value of at least 25% more to protect against possible errors and short circuits.

2b-Other DRC Parameters

Sizes, distances and related variables are also expected to be suitable for the production area. If necessary, it is recommended to increase within a sufficient tolerance range to avoid an error.

After we are sure of all these processes and design, we take our production files, called gerber, from the application we chose for hardware design and start the CAM process.































