Hi ZAV,

I understand you are responsible for the Philips Dynalite integration in home assistant.
Sorry for the strange method of contact, this was the only thing I could think of to reach out to you.


I have been working on a lot of sites using the HA Philips Dynalite Integration recently, and got the opportunity to get some help form a local Australia Dynalite expert.
He's made some massive improvements on the integration..

Below are links to his repositories, and videos showing new functionality including 
- Changed On operation for a HA Light. Instead of recalling a DyNet 100% channel level command. It will recall a DyNet Preset 1 command for this specific channel.
- Introduced more efficient method for tracking DyNet Presets in HA. On initial reception of a DyNet preset the channel levels are requested and this value is stored. on subsequent Dynet presets this stored value is used.
- introduced a method for ensuring DyNet user interfaces like button panels and sensors remain synchronised. (e.g. If a toggling button sends preset commands to all channels in an area, Then it should be notified when the first channel turns on or last channel turns off in that area)  Each time a HA light level changes my code checks the other channels in the area. if it is the first to go on or the last to go off then a Dynet command is sent to notify DyNet user interfaces.
- found HA driver was not able to sync on DyNet 2 packets. This may result in missed DyNet 1 Packets. Changed packet handling so that these packets can be recognised appropriately.

https://github.com/starry-au
https://autele.sharepoint.com/:v:/s/support/EXiScWbLWZJCoOxejJOIaB8B0mBfZ6cJNXzQ3SgzOZOEuw?e=ot2nRI
https://autele.sharepoint.com/:v:/s/support/EaZ8Kp41LV9OmT8jvPpMZ28BDJ5_v6LLOtsCpI8cwn8zXw?e=NqmLFF 
https://autele.sharepoint.com/:v:/s/support/EXtd8lMWtwVDjmA5Th8C9u4BpYKmI5WG4DIeg77CU4c1mQ?e=I0DEoj

My question is how would I go about requesting his enhancements are included in main branch of HA so I can continue to keep instances using this updated?
