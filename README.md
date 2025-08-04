# ez-bake-lithography
Low cost silicon lithography machine

Aliexpress "EPROM ERASER" ("ay-fw-ccq" PCB inside):
  * Buy a teal EPROM eraser (ex: https://www.aliexpress.us/item/3256802806741194.html)
    * Should be about $30 delivered
  * Print ay-fw-ccq_carrier_r4.stl

PE-140T version:
  * Buy a Spectroline PE-140T
    * Surplus price varies wildly. However you can get it without the drawer => cheaper unit
    * Remove the bottom cover
    * Bypass the interlock (ex: shim it)
  * Print pe140t_carrier_r1.stl
  * Print wafer-holder_r2.stl

Regardless, for each mask:
  * Print transparency-frame_inner_r1.stl
  * Print transparency-frame_outer_r1.stl
  * I had to run the transparency through my printer twice for it to be reasonably dark
  * Cut out the mask from the transparency

Reference transparency flow
  * Transparency: Uinkit https://www.amazon.com/dp/B078R4DGSB?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1
  * Printer: Brother HL-L2390DW
  * Linux print: settings => no scaling
  * Put transparency in the main paper tray as the only thing in there
    * Its hard to feed from the side feeder with consistent alignment
  * Print => 2 copies
  * Let it print the first pass / copy
  * Without rotating or flipping, feed it into the tray a second time
    * If you do try feeding from the side, you need to flip it over vertically
  * Let it print the second pass / copy
  * Check alignment
    * Usually upper right is best aligned
    * Try again if it doesn't look right
  * General tips
    * It jammed a lot. Its not a fun process
    * Adjusting Windows driver toner darkness (official brother driver) did nothing
    * I don't see a printer menu setting to adjust toner darkness

Reference developing flow
  * Spin on photoresist
    * P4620 photoresist
    * Use Maasi spin coater
    * ~0.8 mL
    * 2" wafer
    * 4200 RPM @ 30 sec
  * Soft bake phototresist
    * 3 minutes @ 125C on hot plate
  * Exposure
    * PE-140T: expose for 15 minutes
  * Develop
    * 200 to 500 mL of 18% w/v KOH solution
      * Aim for 300 mL min
      * Ex for 300 mL
        * 54 g KOH
        * 300 mL DI H2O
      * Smaller amounts of solution lead to inconsistent developing
    * Using carbon fiber tweezers, waft wafer for ~30 seconds
    * Waft in 300 mL DI water (tank 1) until photoresist think clouds are gone (~10 seconds)
    * Waft in 300 mL DI water (tank 2) for final clean
    * Optional: spin and/or blow dry for best result
  * Inspect under microscope
    * If you have done this correctly you should see no photoresist on wafer and still photoresist where the pattern was

More notes here: https://docs.google.com/document/d/17HMt2Zzm5FRwCRLVQvpPXudmmuqpur_HYsEFmfIFAqE/edit?tab=t.0#heading=h.3smdsrxmfbn6

