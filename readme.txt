The Build Spawner-
Mod that gives players The Build Spawner's to spawn build

How to add build 
---code---
minetest.register_craftitem("the_build_spawner:build", {
	description = "build",
	inventory_image = "build.png",
	on_place = function(itemstack, placer, pointed_thing)
		if pointed_thing.above then
			local file = io.open(minetest.get_modpath("the_build_spawner").."/schemes/build.we")
			local value = file:read("*a")
			file:close()
			local p = pointed_thing.above
			p.y = p.y - 1
			p.x = p.x - 0
			p.z = p.z - 0
			local count = worldedit.deserialize(pointed_thing.above, value)
			itemstack:take_item()
		end
		return itemstack
	end,
})
--------------

For add build do as following-
1)insert your Build_name in "minetest.register_craftitem"
2)Insert you build description or your build_name in description
3)Insert file nameto locate you file like this
(minetest.get_modpath("the_build_spawner").."/schemes/build.we")

leave all code same, for your build to be added,just rename your builds name as you want .
