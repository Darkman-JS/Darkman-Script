// ==UserScript==
// @name         SUPREMO HACK!
// @namespace    http://tampermonkey.net/
// @version      2.5
// @author       ⒹⒶⓇⓀⓂⒶⓃ
// @match        http://bloble.io/*
// @grant        none
// ==/UserScript==

//BaseBuilder

window.UIList = window.UIList || [];
window.initFuncs = window.initFuncs || [];
window.statusItems = window.statusItems || [];


window.UIList.push({
    level: 0,
    x: 0,
    html: '<div onclick=powerPlants()>Upgrade Power Plants</div>'
}, {
    level: 0,
    x: 1,
    html: '<div onclick=microGenerators()>Upgrade Micro-Generators</div>'
}, {
    level: 0,
    x: 2,
    html: '<div onclick=antiTank()>Upgrade Anti-Tanks</div>'
}, {
    level: 1,
    x: 0,
    html: '<div onclick=sellGenerators()>Sell generators</div>'
}, {
    level: 1,
    x: 1,
    html: '<div onclick=sellall()>Sell All</div>'
}, {
    level: 1,
    x: 2,
    html: '<div onclick=sellhouses()>Sell Houses</div>'
}, {
    level: 1,
    x: 3,
    html: '<div onclick=sellwalls()>Sell Walls</div>'
}, {
    level: 1,
    x: 4,
    html: '<div onclick=sellinner()>Sell Inner</div>'
}, {
    level: 1,
    x: 5,
    html: '<div onclick=sellouter()>Sell Outer</div>'
}, {
    level: 2,
    x: 0,
    html: '<div onclick=gatlins()>Upgrade Gatlins</div>'
}, {
    level: 2,
    x: 1,
    html: '<div onclick=spotter()>Upgrade Spotter</div>'
}, {
    level: 2,
    x: 2,
    html: '<div onclick=semiAuto()>Upgrade Semi-Auto</div>'
}, {
    level: 2,
    x: 3,
    html: '<div onclick=kill()>-</div>'
}, {
    level: 2,
    x: 4,
    html: '<div onclick=bot()>Bots</div>'
}, {
    level: 2,
    x: 5,
    html: '<div onclick=add()>+</div>'
}, {
    level: 3,
    x: 0,
    html: '<div onclick=buildFullDefend1()>Build Def1</div>'
}, {
    level: 3,
    x: 1,
    html: '<div onclick=buildFullDefend2()>Build Def2</div>'
}, {
    level: 3,
    x: 2,
    html: '<div onclick=buildHybrid()>Build HYB1</div>'
}, {
    level: 3,
    x: 3,
    html: '<div onclick=buildHybrid2()>Build HYB2</div>'
}, {
    level: 3,
    x: 4,
    html: '<div onclick=buildHousesandTurrets()>Build Houses+Tanks</div>'
}, {
    level: 4,
    x: 0,
    html: '<div onclick=boulders()>Upg.Boulders</div>'
}, {
    level: 4,
    x: 1,
    html: '<div onclick=spikes()>Upg.Spikes</div>'
}, {
    level: 4,
    x: 2,
    html: '<div onclick=rapid()>Upg.Rapid</div>'
}, {
    level: 4,
    x: 3,
    html: '<div onclick=ranged()>Upg.Ranged</div>'
}, {
    level: 4,
    x: 4,
    html: '<div onclick=buildWalls()>Build Walls</div>'
}, {
    level: 5,
    x: 0,
    html: '<div onclick=buildGenerators()>Build Gens</div>'
}, {
    level: 5,
    x: 1,
    html: '<div onclick=buildHouses()>Build Houses</div>'
}, {
    level: 5,
    x: 2,
    html: '<div onclick=sellbarracks()>Sell Barracks</div>'
}, {
    level: 5,
    x: 3,
    html: '<div onclick=selltanks()>Sell Tanks</div>'
}, {
    level: 5,
    x: 4,
    html: '<div onclick=sellarmory()>Sell Armory</div>'
}, {
    level: 6,
    x: 0,
    html: '<div onclick=greaterbarracks()>Upgrade Greater Barracks</div>'
}, {
    level: 6,
    x: 1,
    html: '<div onclick=tankfactory()>Upgrade Tank Factory</div>'
}, {
    level: 6,
    x: 2,
    html: '<div onclick=siegefactory()>Upgrade Siege Factory</div>'
}, {
    level: 7,
    x: 0,
    html: '<div onclick=greatleadership()>Great Leadership</div>'
}, {
    level: 7,
    x: 1,
    html: '<div onclick=upgradesoldier()>Upgrade Soldier</div>'
}, {
    level: 7,
    x: 2,
    html: '<div onclick=upgradetanks()>Upgrade Tanks</div>'
}, {
    level: 7,
    x: 3,
    html: '<div onclick=commander()>Commander(criando)</div>'
}, {
});

function emit2() {
    socket.emit.apply(socket, arguments);
}

window.kill = function () {
            local.emit('del',selUnits[0].owner);
        }
window.bot = function () {
var clanTag = prompt('Nick do bot:');
     alert(+socket.io.uri+' '+player.sid+' '+Name+'Bot'+' 0');
    }

var script = document.createElement('script');
script.type = "text/javascript";

window.add = function () {
        local.emit("create");
    }

function emit2() {
    socket.emit.apply(socket, arguments);
}
window.walls = function () {
    for (i = -3.14; i < 3.14; i += .108) emit2("1", i, 1e3, 1)
}
window.sellGenerators = window.sellGenerators || function () {
    for (var a = [], d = 0; d < units.length; ++d) {
        if (units[d].type === 0 && units[d].owner == player.sid) {
            var name = getUnitFromPath(units[d].uPath).name;
            (name === 'Generator' || name === 'Power Plant') && a.push(units[d].id)
        }
    }
    socket.emit("3", a)
}
window.sellhouses = function () {
    for (var a = [], d = 0; d < units.length; ++d) units[d].type === 0 && units[d].owner == player.sid && getUnitFromPath(units[d].uPath).name === 'House' && a.push(units[d].id);
    socket.emit("3", a)
}
window.sellarmory = function () {
    for (var a = [], d = 0; d < units.length; ++d) units[d].type === 0 && units[d].owner == player.sid && getUnitFromPath(units[d].uPath).name === 'Armory' && a.push(units[d].id);
    socket.emit("3", a)
}
window.sellbarracks = function () {
    for (var a = [], d = 0; d < units.length; ++d) {
        if (units[d].type === 2 && units[d].owner == player.sid) {
            var name = getUnitFromPath(units[d].uPath).name;
            (name === 'Barracks' || name === 'Greater Barracks' || name === 'Tank Factory' || name === 'Siege Factory') && a.push(units[d].id)
        }
    }
    socket.emit("3", a)
}
window.selltanks = function () {
    for (var a = [], d = 0; d < units.length; ++d) {
        if (units[d].type === 0 && units[d].owner == player.sid) {
            var name = getUnitFromPath(units[d].uPath).name;
            (name === 'Sniper Turret' || name === 'Semi-Auto Sniper' || name === 'Anti Tank Gun') && a.push(units[d].id)
        }
    }
    socket.emit("3", a)
}
window.sellinner = function () {
    for (var a = [], d = 0; d < units.length; ++d) {
        if (units[d].type === 0 && units[d].owner == player.sid) {
            a.push(units[d].id)
        }
    }
    socket.emit("3", a)
}
window.sellouter = function () {
    for (var a = [], d = 0; d < units.length; ++d)(units[d].type === 3 || units[d].type === 2) && units[d].owner == player.sid && a.push(units[d].id);
    socket.emit("3", a)
}
window.sellwalls = function () {
    for (var a = [], d = 0; d < units.length; ++d) {
        if (units[d].type === 3 && units[d].owner == player.sid) {
            var name = getUnitFromPath(units[d].uPath).name;
            (name === 'Wall' || name === 'Boulder' || name === 'Spikes' || name === 'Micro Generator') && a.push(units[d].id)
        }
    }
    socket.emit("3", a)
}
window.sellall = function () {
    for (var a = [], d = 0; d < units.length; ++d)(units[d].type === 3 || units[d].type === 2 || units[d].type === 0) && units[d].owner == player.sid && a.push(units[d].id);
    socket.emit("3", a)
}
window.boulders = window.boulders || function () {
    for (var i = 0; i < units.length; ++i) 3 == units[i].type && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.greaterbarracks = window.greaterbarracks || function () {
    for (var i = 0; i < units.length; ++i) 2 == units[i].type && "square" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.tankfactory = window.tankfactory || function () {
    for (var i = 0; i < units.length; ++i) 2 == units[i].type && "square" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 1)
}
window.siegefactory = window.siegefactory || function () {
    for (var i = 0; i < units.length; ++i) 2 == units[i].type && "square" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 2)
}
window.greatleadership = window.greatleadership || function () {
    for (var i = 0; i < units.length; ++i) 1 == units[i].type && "star" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.commander = function () {
    for (var i = 0; i < units.length; ++i) 1 == units[i].type && 9 == units[i].turretIndex && "star" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.upgradesoldier = window.upgradesoldier || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.upgradetanks = window.upgradetanks || function () {
    for (var i = 0; i < units.length; ++i).0 == units[i].type && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 1) && socket.emit("4", units[i].id, 2) && socket.emit("4", units[i].id, 3)
}
window.microGenerators = window.microGenerators || function () {
    for (var i = 0; i < units.length; ++i) 3 == units[i].type && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 1)
}
window.spikes = window.spikes || function () {
    for (var i = 0; i < units.length; ++i) 3 == units[i].type && "hexagon" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.powerPlants = window.powerPlants || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && "hexagon" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.rapid = window.rapid || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && 1 == units[i].turretIndex && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.ranged = window.ranged || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && 1 == units[i].turretIndex && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 1)
}
window.antiTank = window.antiTank || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && 4 == units[i].turretIndex && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 1)
}
window.semiAuto = window.semiAuto || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && 4 == units[i].turretIndex && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.gatlins = window.gatlins || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && 2 == units[i].turretIndex && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
}
window.spotter = window.spotter || function () {
    for (var i = 0; i < units.length; ++i) 0 == units[i].type && 3 == units[i].turretIndex && "circle" == units[i].shape && units[i].owner == player.sid && socket.emit("4", units[i].id, 0)
};
window.build = function (instr) {
    instr.forEach((ins) => {
        emit2.apply({}, ins);
    })
}
window.buildWalls = function () {
socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);
socket.emit("1",8.86,311,1);socket.emit("1",9.07,311,1);socket.emit("1",9.28,311,1);socket.emit("1",9.48,311,1);socket.emit("1",9.68,311,1);
socket.emit("1",9.89,311,1);socket.emit("1",10.10,311,1);socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);socket.emit("1",10.70,311,1);
socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);socket.emit("1",11.70,311,1);
socket.emit("1",11.90,311,1);socket.emit("1",12.11,311,1);socket.emit("1",12.32,311,1);socket.emit("1",12.52,311,1);socket.emit("1",12.72,311,1);
socket.emit("1",12.93,311,1);socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);socket.emit("1",13.74,311,1);
socket.emit("1",13.94,311,1);

}
window.buildFullDefend2 = function () {
socket.emit("1",5.065,188,3);socket.emit("1",5.426,185,3);socket.emit("1",6.1375,192,3);socket.emit("1",6.48,185,3);socket.emit("1",7.175,192,3);
socket.emit("1",7.525,190,3);socket.emit("1",1.93,191,3);socket.emit("1",2.28,192,3);socket.emit("1",2.965,187,3);socket.emit("1",3.305,192,3);
socket.emit("1",4.01,182,3);socket.emit("1",4.365,190,3);socket.emit("1",4.9,245.5,3);socket.emit("1",5.25,245.5,3);socket.emit("1",5.6,245.5,3);
socket.emit("1",5.95,245.5,3);socket.emit("1",6.35,245.5,3);socket.emit("1",6.65,245.5,3);socket.emit("1",7,245.5,3);socket.emit("1",7.35,245.5,3);
socket.emit("1",7.7,245.5,3);socket.emit("1",1.75,245.5,3);socket.emit("1",2.1,245.5,3);socket.emit("1",2.475,245.5,3);socket.emit("1",2.8,245.5,3);
socket.emit("1",3.11,245.5,3);socket.emit("1",3.49,245.5,3);socket.emit("1",3.85,245.5,3);socket.emit("1",4.15,245.5,3);socket.emit("1",4.55,245.5,3);
socket.emit("1",4.72,130,1);socket.emit("1",5.21,130,1);socket.emit("1",5.70,130,1);socket.emit("1",6.19,130,1);socket.emit("1",6.68,130,1);
socket.emit("1",7.17,130,1);socket.emit("1",7.65,130,1);socket.emit("1",8.13,130,1);socket.emit("1",8.61,130,1);socket.emit("1",9.09,130,1);
socket.emit("1",9.57,130,1);socket.emit("1",10.05,130,1);socket.emit("1",10.53,130,1);socket.emit("1",5.775,192,5);socket.emit("1",6.825,190,5);
socket.emit("1",1.585,183,5);socket.emit("1",2.619,186,5);socket.emit("1",3.6675,191,5);socket.emit("1",4.725,192,5);
}
window.buildFullDefend1 = function () {
socket.emit("1",4.73,245,3);socket.emit("1",5.0025,245,3);socket.emit("1",5.5475,245,3);socket.emit("1",5.82,245,3);socket.emit("1",6.0925,245,3);
socket.emit("1",6.6375,245,3);socket.emit("1",6.91,245,3);socket.emit("1",7.1825,245,3);socket.emit("1",7.7275,245,3);socket.emit("1",8.0025,245,3);
socket.emit("1",8.5475,245,3);socket.emit("1",8.82,245,3);socket.emit("1",9.0925,245,3);socket.emit("1",9.64,245,3);socket.emit("1",9.9125,245,3);
socket.emit("1",10.1875,245,3);socket.emit("1",10.7375,245,3);socket.emit("1",10.53,130,1);socket.emit("1",10.05,130,1);socket.emit("1",9.57,130,1);
socket.emit("1",9.09,130,1);socket.emit("1",8.61,130,1);socket.emit("1",8.13,130,1);socket.emit("1",7.65,130,1);socket.emit("1",7.17,130,1);
socket.emit("1",6.68,130,1);socket.emit("1",6.19,130,1);socket.emit("1",5.70,130,1);socket.emit("1",5.21,130,1);socket.emit("1",4.72,130,1);
socket.emit("1",10.78,180,1);socket.emit("1",10.3,180,1);socket.emit("1",9.8,180,1);socket.emit("1",9.32,180,1);socket.emit("1",8.85,180,1);
socket.emit("1",8.38,180,1);socket.emit("1",7.88,180,1);socket.emit("1",7.4,180,1);socket.emit("1",6.95,180,1);socket.emit("1",6.45,180,1);
socket.emit("1",5.95,180,1);socket.emit("1",5.47,180,1);socket.emit("1",4.95,180,1);socket.emit("1",5.275,245,5);socket.emit("1",6.365,245,5);
socket.emit("1",7.455,245,5);socket.emit("1",8.275,245,5);socket.emit("1",9.3675,245,5);socket.emit("1",10.4625,245,5);
}
window.buildHybrid2 = function () {
socket.emit("1",5.725,130,3);socket.emit("1",6.225,130,3);socket.emit("1",6.725,130,3);socket.emit("1",2.71,130,3);socket.emit("1",3.21,130,3);
socket.emit("1",3.71,130,3);socket.emit("1",5.065,186,3);socket.emit("1",5.87,192.75,3);socket.emit("1",6.25,196,3);socket.emit("1",1.35,183,3);
socket.emit("1",1.825,183,3);socket.emit("1",3.19,196,3);socket.emit("1",3.565,192.75,3);socket.emit("1",4.375,186,3);socket.emit("1",6.45,245,3);
socket.emit("1",6.8,245,3);socket.emit("1",2.645,245,3);socket.emit("1",2.99,245,3);socket.emit("1",4.72,130,7);socket.emit("1",5.24,130,4);
socket.emit("1",1.1,130,4);socket.emit("1",1.575,130,4);socket.emit("1",2.045,130,4);socket.emit("1",4.2,130,4);socket.emit("1",5.45,185,4);
socket.emit("1",6.625,193,4);socket.emit("1",6.95,187,4);socket.emit("1",7.275,189,4);socket.emit("1",2.17,187,4);socket.emit("1",2.4925,187,4);
socket.emit("1",2.81,193,4);socket.emit("1",4,185,4);socket.emit("1",4.72,212.5,5);socket.emit("1",4.96,245,4);socket.emit("1",5.46,245,4);
socket.emit("1",7.378,245,4);socket.emit("1",7.628,245,4);socket.emit("1",7.878,245,4);socket.emit("1",8.128,245,4);socket.emit("1",2.0975,245,4);
socket.emit("1",3.975,245,4);socket.emit("1",4.475,245,4);socket.emit("1",2.375,245,5);socket.emit("1",6.05,245,5);socket.emit("1",7.1,245,5);
socket.emit("1",3.385,245,5);socket.emit("1",5.21,245,1);socket.emit("1",5.71,245,1);socket.emit("1",3.725,245,1);socket.emit("1",4.225,245,1);
socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);
socket.emit("1",8.86,311,1);socket.emit("1",9.06,311,1);socket.emit("1",9.26,311,1);socket.emit("1",9.46,311,1);socket.emit("1",9.66,311,1);
socket.emit("1",9.86,311,1);socket.emit("1",10.28,311,1);socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);
socket.emit("1",11.30,311,1);socket.emit("1",11.72,311,1);socket.emit("1",12.14,311,1);socket.emit("1",12.34,311,1);socket.emit("1",12.54,311,1);
socket.emit("1",12.74,311,1);socket.emit("1",12.94,311,1);socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);
socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);socket.emit("1",10.07,311,8);socket.emit("1",10.49,311,8);socket.emit("1",11.51,311,8);
socket.emit("1",11.93,311,8);
}
window.buildHousesandTurrets = function () {
socket.emit("1",4.725,130,7);socket.emit("1",3.985,183,5);socket.emit("1",5.475,183,5);socket.emit("1",6.47,184,5);socket.emit("1",7.85,186,5);
socket.emit("1",9.26,183,5);socket.emit("1",5.245,130,4);socket.emit("1",5.725,130,4);socket.emit("1",6.205,130,4);socket.emit("1",6.675,130,4);
socket.emit("1",7.145,130,4);socket.emit("1",7.615,130,4);socket.emit("1",8.085,130,4);socket.emit("1",8.555,130,4);socket.emit("1",9.025,130,4);
socket.emit("1",3.225,130,4);socket.emit("1",9.975,130,4);socket.emit("1",10.485,130,4);socket.emit("1",4.72,210,4);socket.emit("1",5.06,185,4);
socket.emit("1",5.81,189,4);socket.emit("1",6.13,190,4);socket.emit("1",6.81,187,4);socket.emit("1",7.13,191,4);socket.emit("1",7.45,185,4);
socket.emit("1",8.25,185,4);socket.emit("1",8.6,190,4);socket.emit("1",8.92,189,4);socket.emit("1",9.6,189,4);socket.emit("1",9.925,190,4);
socket.emit("1",4.39,185,4);socket.emit("1",4.94,246,4);socket.emit("1",5.1875,246,4);socket.emit("1",5.435,246,4);socket.emit("1",5.685,246,4);
socket.emit("1",5.935,246,4);socket.emit("1",6.24,246,4);socket.emit("1",6.49,246,4);socket.emit("1",6.74,246,4);socket.emit("1",6.99,246,4);
socket.emit("1",7.25,246,4);socket.emit("1",7.5,246,4);socket.emit("1",7.75,246,4);socket.emit("1",8,246,4);socket.emit("1",8.25,246,4);
socket.emit("1",8.5,246,4);socket.emit("1",8.75,246,4);socket.emit("1",9.01,246,4);socket.emit("1",9.26,246,4);socket.emit("1",9.51,246,4);
socket.emit("1",9.76,246,4);socket.emit("1",10.03,246,4);socket.emit("1",4,246,4);socket.emit("1",4.25,246,4);socket.emit("1",4.5,246,4);
socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);
socket.emit("1",8.86,311,1);socket.emit("1",9.28,311,1);socket.emit("1",9.48,311,1);socket.emit("1",9.68,311,1);socket.emit("1",10.10,311,1);
socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);
socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);socket.emit("1",11.70,311,1);socket.emit("1",11.90,311,1);socket.emit("1",12.32,311,1);
socket.emit("1",12.52,311,1);socket.emit("1",12.72,311,1);socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);
socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);socket.emit("1",9.07,311,8);socket.emit("1",9.89,311,8);socket.emit("1",12.11,311,8);
socket.emit("1",12.93,311,8);
}
window.buildHybrid = function () {
socket.emit("1",7.615,245,1);
socket.emit("1",4.945,245,1);socket.emit("1",4.725,130,7);socket.emit("1",5.245,130,1);socket.emit("1",5.715,130,1);socket.emit("1",4.205,130,1);
socket.emit("1",3.735,130,1);socket.emit("1",4.725,210.5,4);socket.emit("1",5.205,245,3);socket.emit("1",5.075,186.1,3);socket.emit("1",5.46,182.5,5);
socket.emit("1",5.46,245,1);socket.emit("1",5.71,245.5,4);socket.emit("1",5.81,188.5,1);socket.emit("1",5.964,245,3);socket.emit("1",6.182,130,1);
socket.emit("1",6.135,190,1);socket.emit("1",6.278,245,3);socket.emit("1",6.668,130,1);socket.emit("1",6.47,184,5);socket.emit("1",6.534,245,1);
socket.emit("1",6.78,245,4);socket.emit("1",6.855,185,3);socket.emit("1",7.134,130,1);socket.emit("1",7.035,245,3);socket.emit("1",7.19,190,1);
socket.emit("1",7.335,245,3);socket.emit("1",7.6,130,1);socket.emit("1",7.51,189,1);
}
window.buildHouses = function () {
socket.emit("1",4.725,130,7);socket.emit("1",5.245,130,4);socket.emit("1",5.715,130,4);socket.emit("1",6.185,130,4);socket.emit("1",6.655,130,4);
socket.emit("1",7.13,130,4);socket.emit("1",7.6,130,4);socket.emit("1",1.85,130,4);socket.emit("1",2.32,130,4);socket.emit("1",2.79,130,4);
socket.emit("1",3.265,130,4);socket.emit("1",3.735,130,4);socket.emit("1",4.205,130,4);socket.emit("1",5.06,185,4);socket.emit("1",5.4,185,4);
socket.emit("1",5.725,190,4);socket.emit("1",6.045,186,4);socket.emit("1",6.374,185,4);socket.emit("1",6.7215,189.5,4);socket.emit("1",7.0425,188.5,4);
socket.emit("1",7.365,185,4);socket.emit("1",7.712,187.45,4);socket.emit("1",8.035,188.5,4);socket.emit("1",8.36,185,4);socket.emit("1",2.425,188,4);
socket.emit("1",2.75,190,4);socket.emit("1",3.075,184,4);socket.emit("1",3.42,186,4);socket.emit("1",3.74,190,4);socket.emit("1",4.06,186,4);
socket.emit("1",4.39,185,4);socket.emit("1",4.8625,245,4);socket.emit("1",5.1125,245,4);socket.emit("1",5.3625,245,4);socket.emit("1",5.6125,245,4);
socket.emit("1",5.8625,245,4);socket.emit("1",6.1125,245,4);socket.emit("1",6.3625,245,4);socket.emit("1",6.6125,245,4);socket.emit("1",6.8625,245,4);
socket.emit("1",7.14,245,4);socket.emit("1",7.39,245,4);socket.emit("1",7.64,246,4);socket.emit("1",7.89,246,4);socket.emit("1",8.14,246,4);
socket.emit("1",8.39,246,4);socket.emit("1",8.635,246,4);socket.emit("1",8.885,246,4);socket.emit("1",2.5825,245,4);socket.emit("1",2.8625,245,4);
socket.emit("1",3.1125,245,4);socket.emit("1",3.3625,245,4);socket.emit("1",3.6125,245,4);socket.emit("1",3.8625,245,4);socket.emit("1",4.1125,245,4);
socket.emit("1",4.3625,245,4);socket.emit("1",4.6125,245,4);socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);
socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);socket.emit("1",8.86,311,1);socket.emit("1",9.28,311,1);socket.emit("1",9.48,311,1);
socket.emit("1",9.68,311,1);socket.emit("1",10.10,311,1);socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);socket.emit("1",10.70,311,1);
socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);socket.emit("1",11.70,311,1);
socket.emit("1",11.90,311,1);socket.emit("1",12.32,311,1);socket.emit("1",12.52,311,1);socket.emit("1",12.72,311,1);socket.emit("1",13.14,311,1);
socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);socket.emit("1",9.07,311,8);
socket.emit("1",9.89,311,8);socket.emit("1",12.11,311,8);socket.emit("1",12.93,311,8);
}
window.buildGenerators = function () {
socket.emit("1",4.73,245,3),socket.emit("1",5.0025,245,3),socket.emit("1",5.275,245,3),socket.emit("1",5.5475,245,3),socket.emit("1",5.82,245,3);
socket.emit("1",6.0925,245,3),socket.emit("1",6.365,245,3),socket.emit("1",6.6375,245,3),socket.emit("1",6.91,245,3),socket.emit("1",7.1825,245,3);
socket.emit("1",7.455,245,3),socket.emit("1",7.7275,245,3),socket.emit("1",8.0025,245,3),socket.emit("1",8.275,245,3),socket.emit("1",8.5475,245,3);
socket.emit("1",8.82,245,3),socket.emit("1",9.0925,245,3),socket.emit("1",9.3675,245,3),socket.emit("1",9.64,245,3),socket.emit("1",9.9125,245,3);
socket.emit("1",10.1875,245,3);socket.emit("1",10.4625,245,3);socket.emit("1",10.7375,245,3);socket.emit("1",5.999,180,3);socket.emit("1",6.275,130,3);
socket.emit("1",6.51,185,3);socket.emit("1",6.775,130,3);socket.emit("1",7.05,185,3);socket.emit("1",7.3,130,3);socket.emit("1",7.6,185,3);
socket.emit("1",7.85,130,3);socket.emit("1",8.15,185,3);socket.emit("1",8.4,130,3);socket.emit("1",8.675,185,3);socket.emit("1",8.925,130,3);
socket.emit("1",9.225,185,3);socket.emit("1",9.5,130,3);socket.emit("1",9.78,185,3);socket.emit("1",10.05,130,3);socket.emit("1",10.325,185,3);
socket.emit("1",10.6,130,3);socket.emit("1",4.5889,186.5,3);socket.emit("1",4.81,130,3);socket.emit("1",5.085,180.5,3);socket.emit("1",5.36,130,3);
socket.emit("1",5.64,180,3);
}
window.makeUI = function () {
    if (window.hasMadeUI) return;
    window.hasMadeUI = true;
    window.statusItems.sort(function (a, b) {
        return a.order - b.order;
    })
    var levels = [];
    window.UIList.forEach((item) => {
        if (!levels[item.level]) levels[item.level] = [];
        levels[item.level].push(item)
    })

    levels = levels.filter((a) => {
        if (a) {
            a.sort(function (a, b) {
                return a.x - b.x;
            })
            return true;
        } else {
            return false;
        }
    })

    var headAppend = document.getElementsByTagName("head")[0],
style = document.createElement("div");

    var toast = document.createElement('div');
    toast.id = "snackbar";
    var css = document.createElement('div');

    css.innerHTML = '<style>\n\
#snackbar {\n\
    visibility: hidden;\n\
    min-width: 250px;\n\
    margin-left: -125px;\n\
    background-color: rgba(40, 40, 40, 0.5);\n\
    color: #fff;\n\
    text-align: center;\n\
    border-radius: 4px;\n\
    padding: 10px;\n\
    font-family: "regularF";\n\
    font-size: 20px;\n\
    position: fixed;\n\
    z-index: 100;\n\
    left: 50%;\n\
    top: 30px;\n\
}\n\
#snackbar.show {\n\
    visibility: visible;\n\
    -webkit-animation: fadein 0.5s;\n\
    animation: fadein 0.5s;\n\
}\n\
#snackbar.hide {\n\
    visibility: visible;\n\
    -webkit-animation: fadeout 0.5s;\n\
    animation: fadeout 0.5s;\n\
}\n\
@-webkit-keyframes fadein {\n\
    from {top: 0; opacity: 0;}\n\
    to {top: 30px; opacity: 1;}\n\
}\n\
@keyframes fadein {\n\
    from {top: 0; opacity: 0;}\n\
    to {top: 30px; opacity: 1;}\n\
}\n\
@-webkit-keyframes fadeout {\n\
    from {top: 30px; opacity: 1;}\n\
    to {top: 0; opacity: 0;}\n\
}\n\
@keyframes fadeout {\n\
    from {top: 30px; opacity: 1;}\n\
    to {top: 0; opacity: 0;}\n\
}\n\
</style>'
    var height = levels.length * (14 + 19) + (levels.length - 1) * 7 + 15;
    style.innerHTML = "<style>\n\
#noobscriptUI, #noobscriptUI > div > div {\n\
    background-color:rgba(40,40,40,.5);\n\
    margin-left: 3px;\n\
    border-radius:4px;\n\
    pointer-events:all\n\
}\n\
#noobscriptUI {\n\
    top: -" + (height + 12) + "px;\n\
    transition: 1s;\n\
    margin-left:10px;\n\
    position:absolute;\n\
    padding-left:24px;\n\
    margin-top:9px;\n\
    padding-top:15px;\n\
    width:580px;\n\
    height: " + height + "px;\n\
    font-family:arial;\n\
    left:25%\n\
}\n\
#noobscriptUI:hover{\n\
    top:0px\n\
}\n\
#noobscriptUI > div > div {\n\
    color:#fff;\n\
    padding:7px;\n\
    height:19px;\n\
    display:inline-block;\n\
    cursor:pointer;\n\
    font-size:15px\n\
}\n\
</style>"

    headAppend.appendChild(style);
    headAppend.appendChild(css);


    var contAppend = document.getElementById("gameUiContainer"),
        menuA = document.createElement("div");

    var code = ['<div id="noobscriptUI">\n'];

    levels.forEach((items, i) => {
        code.push(i === 0 ? '    <div>\n' : '    <div style="margin-top:7px;">\n');
        items.forEach((el) => {
            code.push('        ' + el.html + '\n');
        })
        code.push('    </div>\n');
    })
    code.push('    <div id="confinfo" style="margin-top:4px; color: white; text-align: center; font-size: 10px; white-space:pre"></div>')
    code.push('</div>');

    menuA.innerHTML = code.join("");
    contAppend.insertBefore(menuA, contAppend.firstChild)
    contAppend.appendChild(toast)
    var toastTimeout = false;
    window.showToast = function (msg) {
        toast.textContent = msg;

        if (toastTimeout) clearTimeout(toastTimeout);
        else toast.className = "show";
        toastTimeout = setTimeout(function () {
            toast.className = 'hide'
            setTimeout(function () {
                toast.className = '';
            }, 400);
            toastTimeout = false;
        }, 3000);
    }
    window.statusBar = function () {
        var el = document.getElementById('confinfo');
        var text = [];

        window.statusItems.forEach((item, i) => {
            if (i !== 0) text.push('     ');
            if (item.name) text.push(item.name + ': ');
            text.push(item.value());
        })

        el.textContent = text.join('');
    }
    window.statusBar();

    window.initFuncs.forEach((func) => {
        func();
    })
}
setTimeout(() => {
    window.makeUI();
}, 1000)

//InstaFind

var gotoUsers = [];
var gotoIndex = 0;
window.overrideSocketEvents = window.overrideSocketEvents || [];
window.chatCommands = window.chatCommands || {};

window.chatCommands.find = function(split) {
    var name = split.slice(1).join(' ');
    if (name == '') {
        addChat('Please specify a username', 'Client')
        return;
    }
    window.goto(name)
}
window.overrideSocketEvents.push({
    name: "l",
    description: "Leaderboard Insta Find override",
    func: function(a) {
        var d = "",
            c = 1,
            b = 0;
        for (; b < a.length;) {
            d += "<div class='leaderboardItem' onclick=goto2(" + a[b] + ");><div style='display:inline-block;float:left;' class='whiteText'>" + c + ".</div> <div class='" + (player && a[b] == player.sid ? "leaderYou" : "leader") + "'>" + a[b + 1] + "</div><div class='scoreText'>" + a[b + 2] + "</div></div>", c++, b += 3;
        }
        leaderboardList.innerHTML = d;
    }
})
leaderboardList.style.pointerEvents = 'auto';
chatListWrapper.style.pointerEvents = 'auto';

window.goto = function(username) {
    gotoUsers = users.filter((user) => {
        return user.name === username
    });
    gotoIndex = 0;
    if (gotoUsers[0]) {
        camX = gotoUsers[0].x - player.x;
        camY = gotoUsers[0].y - player.y;
    }
    addChat(gotoUsers.length + ' users found with the name ' + username, 'Client');
    return gotoUsers.length;
}
window.goto2 = function(id, go) {
    gotoUsers = users.filter((user) => {
        return user.sid === id;
    });
    gotoIndex = 0;
    if (!go && gotoUsers[0]) {
        camX = gotoUsers[0].x - player.x;
        camY = gotoUsers[0].y - player.y;
    }
    return gotoUsers.length;
}

window.gotoLeft = function() {
    if (!gotoUsers.length) return;

    if (camX == gotoUsers[gotoIndex].x - player.x && camY == gotoUsers[gotoIndex].y - player.y) {
        if (gotoIndex <= 0) gotoIndex = gotoUsers.length;
        gotoIndex--;
    }
    camX = gotoUsers[gotoIndex].x - player.x;
    camY = gotoUsers[gotoIndex].y - player.y;
}

window.gotoRight = function() {
    if (!gotoUsers.length) return;

    if (camX == gotoUsers[gotoIndex].x - player.x && camY == gotoUsers[gotoIndex].y - player.y) {
        if (gotoIndex >= gotoUsers.length - 1) gotoIndex = -1;
        gotoIndex++;
    }
    camX = gotoUsers[gotoIndex].x - player.x;
    camY = gotoUsers[gotoIndex].y - player.y;
}

window.addChat = function(msg, from, color) {
    color = color || "#fff";
    var b = document.createElement("li");
    b.className = "chatother";
    b.innerHTML = '<span style="color:' + color + '">[' + from + ']</span> <span class="chatText">' + msg + "</span>";
    10 < chatList.childNodes.length && chatList.removeChild(chatList.childNodes[0]);
    chatList.appendChild(b)
}
window.resetCamera = function() { // Override
    camX = camXS = camY = camYS = 0;
    cameraKeys = {
        l: 0,
        r: 0,
        u: 0,
        d: 0
    }

    if (socket && window.overrideSocketEvents && window.overrideSocketEvents.length) {
        window.overrideSocketEvents.forEach((item) => {
            socket.removeAllListeners(item.name)
            socket.on(item.name, item.func);

        });

    }
}

window.addChatLine = function(a, d, c) {
    if (player) {
        var b = getUserBySID(a);
        if (c || 0 <= b) {
            var g = c ? "SERVER" : users[b].name;
            c = c ? "#fff" : playerColors[users[b].color] ? playerColors[users[b].color] : playerColors[0];
            player.sid == a && (c = "#fff");
            b = document.createElement("li");
            b.className = player.sid == a ? "chatme" : "chatother";

            b.innerHTML = '<span style="color:' + c + '" onclick=goto2(' + a + ');>[' + g + ']</span> <span class="chatText">' + d + "</span>";
            10 < chatList.childNodes.length && chatList.removeChild(chatList.childNodes[0]);
            chatList.appendChild(b)
        }
    }
}

window.addEventListener("keyup", function(a) {
    a = a.keyCode ? a.keyCode : a.which;
    if (a === 190) {
        window.gotoRight()
    } else if (a === 188) {
        window.gotoLeft();
    }

});

//Zoom

var scroll = 0;

mainCanvas.addEventListener ? (window.addEventListener("mousewheel", zoom, !1),
                               mainCanvas.addEventListener("DOMMouseScroll", zoom, !1)) : window.attachEvent("onmousewheel", zoom);

function zoom(a) {
    a = window.event || a;
    a.preventDefault();
    a.stopPropagation();
    scroll = Math.max(-1, Math.min(1, a.wheelDelta || -a.detail))
    if (scroll == -1) { //zoom out
        if (maxScreenHeight < 100000) {
            (maxScreenHeight += 500, maxScreenWidth += 500, resize());
            scroll = 10
        }
    }

    if (scroll == 1) { //zoom in
        if (maxScreenHeight > 1000) {
            (maxScreenHeight -= 250, maxScreenWidth -= 250, resize())
            scroll = 0
        }
    }
}

mainCanvas.onkeydown = function(event) {
    var k = event.keyCode ? event.keyCode : event.which;
    if (k == 70) { // F to zoom out
        if (maxScreenHeight < 10000) {
            (maxScreenHeight += 250, maxScreenWidth += 250, resize());
        }
    }
    if (k == 67) {// C to zoom in
        if (maxScreenHeight > 1000) {
            (maxScreenHeight -= 250, maxScreenWidth -= 250, resize())
        }

    }

    {if(65==a||37==a)cameraKeys.l=0,updateCameraInput();if(68==a||39==a)cameraKeys.r=0,updateCameraInput();if(87==a||38==a)cameraKeys.u=0,updateCameraInput();if(83==a||40==a)cameraKeys.d=0,updateCameraInput();if(32==a){var d=unitList.indexOf(activeUnit);sendUnit(d)}void 0!=upgrInputsToIndex["k"+a]&&toggleActiveUnit(upgrInputsToIndex["k"+a]);46==a&&selUnits.length&&sellSelUnits();84==a&&toggleChat("none"==chatListWrapper.style.display);
     27==a&&(toggleActiveUnit(),disableSelUnit(),showSelector=!1);82==a&&(camY=camX=0)}};mainCanvas.onkeydown=function(a){a=a.keyCode?a.keyCode:a.which;socket&&player&&!player.dead&&(65!=a&&37!=a||cameraKeys.l||(cameraKeys.l=-1,cameraKeys.r=0,updateCameraInput()),68!=a&&39!=a||cameraKeys.r||(cameraKeys.r=1,cameraKeys.l=0,updateCameraInput()),87!=a&&38!=a||cameraKeys.u||(cameraKeys.u=-1,cameraKeys.d=0,updateCameraInput()),83!=a&&40!=a||cameraKeys.d||(cameraKeys.d=1,cameraKeys.u=0,updateCameraInput()))}

addEventListener("keydown", function(a) {
    if (a.keyCode == 77){
        for(i=0;i<users.length;++i){
            if(users[i].name.startsWith("[G]")&&users[i].name !== player.name){
                camX = users[i].x-player.x;
                camY = users[i].y-player.y;
            }
        }
    }
    if (a.keyCode == 113) {//Defend Full Defense
socket.emit("1",4.73,245,1);socket.emit("1",5.0025,245,1);socket.emit("1",5.5475,245,1);socket.emit("1",5.82,245,1);socket.emit("1",6.0925,245,1);
socket.emit("1",6.6375,245,1);socket.emit("1",6.91,245,1);socket.emit("1",7.1825,245,1);socket.emit("1",7.7275,245,1);socket.emit("1",8.0025,245,1);
socket.emit("1",8.5475,245,1);socket.emit("1",8.82,245,1);socket.emit("1",9.0925,245,1);socket.emit("1",9.64,245,1);socket.emit("1",9.9125,245,1);
socket.emit("1",10.1875,245,1);socket.emit("1",10.7375,245,1);socket.emit("1",10.53,130,1);socket.emit("1",10.05,130,1);socket.emit("1",9.57,130,1);
socket.emit("1",9.09,130,1);socket.emit("1",8.61,130,1);socket.emit("1",8.13,130,1);socket.emit("1",7.65,130,1);socket.emit("1",7.17,130,1);
socket.emit("1",6.68,130,1);socket.emit("1",6.19,130,1);socket.emit("1",5.70,130,1);socket.emit("1",5.21,130,1);socket.emit("1",4.72,130,1);
socket.emit("1",10.78,180,1);socket.emit("1",10.3,180,1);socket.emit("1",9.8,180,1);socket.emit("1",9.32,180,1);socket.emit("1",8.85,180,1);
socket.emit("1",8.38,180,1);socket.emit("1",7.88,180,1);socket.emit("1",7.4,180,1);socket.emit("1",6.95,180,1);socket.emit("1",6.45,180,1);
socket.emit("1",5.95,180,1);socket.emit("1",5.47,180,1);socket.emit("1",4.95,180,1);socket.emit("1",5.275,245,1);socket.emit("1",6.365,245,1);
socket.emit("1",7.455,245,1);socket.emit("1",8.275,245,1);socket.emit("1",9.3675,245,1);socket.emit("1",10.4625,245,1);socket.emit("1",7.86,311,1);
socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);socket.emit("1",8.86,311,1);
socket.emit("1",9.07,311,1);socket.emit("1",9.28,311,1);socket.emit("1",9.48,311,1);socket.emit("1",9.68,311,1);socket.emit("1",9.89,311,1);
socket.emit("1",10.10,311,1);socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);
socket.emit("1",11.10,311,1);socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);socket.emit("1",11.70,311,1);socket.emit("1",11.90,311,1);
socket.emit("1",12.11,311,1);socket.emit("1",12.32,311,1);socket.emit("1",12.52,311,1);socket.emit("1",12.72,311,1);socket.emit("1",12.93,311,1);
socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);
    }
    if (a.keyCode == 117) {//Defend 1ªHybrid Base
socket.emit("1",2.205,189.5,1);socket.emit("1",2.88,245,1);socket.emit("1",6.486,185,1);socket.emit("1",2.5425,184,1);socket.emit("1",5.725,130,1);
socket.emit("1",9.975,130,1);socket.emit("1",6.875,184,1);socket.emit("1",4.375,186,1);socket.emit("1",5.065,187,1);socket.emit("1",6,245,1);
socket.emit("1",6.295,245,1);socket.emit("1",7.07,245,1);socket.emit("1",7.358,245,1);socket.emit("1",2.05,245,1);socket.emit("1",2.375,245,1);
socket.emit("1",3.1375,245,1);socket.emit("1",3.445,245,1);socket.emit("1",4.725,130,1);socket.emit("1",6.205,130,1);socket.emit("1",6.675,130,1);
socket.emit("1",7.145,130,1);socket.emit("1",7.615,130,1);socket.emit("1",8.085,130,1);socket.emit("1",8.555,130,1);socket.emit("1",9.025,130,1);
socket.emit("1",9.495,130,1);socket.emit("1",10.475,130,1);socket.emit("1",5.245,130,1);socket.emit("1",4.72,210,1);socket.emit("1",5.475,183,1);
socket.emit("1",5.825,193,1);socket.emit("1",6.15,190,1);socket.emit("1",7.215,190,1);socket.emit("1",7.535,190,1);socket.emit("1",1.565,200,1);
socket.emit("1",1.88,189,1);socket.emit("1",2.95,184,1);socket.emit("1",3.283,190,1);socket.emit("1",3.61,193,1);socket.emit("1",3.95,183,1);
socket.emit("1",5.687,245,1);socket.emit("1",6.56,245,1);socket.emit("1",3.75,245,1);socket.emit("1",4.94,245,1);socket.emit("1",5.1875,245,1);
socket.emit("1",5.435,245,1);socket.emit("1",6.81,245,1);socket.emit("1",7.65,245,1);socket.emit("1",1.75,245,1);socket.emit("1",2.6325,245,1);
socket.emit("1",4,245,1);socket.emit("1",4.25,245,1);socket.emit("1",4.5,245,1);socket.emit("1",4.72,311,1);socket.emit("1",4.92,311,1);
socket.emit("1",5.12,311,1);socket.emit("1",5.32,311,1);socket.emit("1",5.52,311,1);socket.emit("1",5.94,311,1);socket.emit("1",6.14,311,1);
socket.emit("1",6.34,311,1);socket.emit("1",6.54,311,1);socket.emit("1",6.96,311,1);socket.emit("1",7.16,311,1);socket.emit("1",7.36,311,1);
socket.emit("1",7.56,311,1);socket.emit("1",7.76,311,1);socket.emit("1",7.96,311,1);socket.emit("1",8.16,311,1);socket.emit("1",8.36,311,1);
socket.emit("1",8.56,311,1);socket.emit("1",8.76,311,1);socket.emit("1",9.18,311,1);socket.emit("1",9.38,311,1);socket.emit("1",9.58,311,1);
socket.emit("1",9.78,311,1);socket.emit("1",10.2,311,1);socket.emit("1",10.4,311,1);socket.emit("1",10.6,311,1);socket.emit("1",10.8,311,1);
socket.emit("1",5.73,311,1);socket.emit("1",6.75,311,1);socket.emit("1",8.97,311,1);socket.emit("1",9.99,311,1);
    }
    if (a.keyCode == 118) {//Defend 2ªHybrid Base
socket.emit("1",5.725,130,1);socket.emit("1",6.225,130,1);socket.emit("1",6.725,130,1);socket.emit("1",2.71,130,1);socket.emit("1",3.21,130,1);
socket.emit("1",3.71,130,1);socket.emit("1",5.065,186,1);socket.emit("1",5.87,192.75,1);socket.emit("1",6.25,196,1);socket.emit("1",1.35,183,1);
socket.emit("1",1.825,183,1);socket.emit("1",3.19,196,1);socket.emit("1",3.565,192.75,1);socket.emit("1",4.375,186,1);socket.emit("1",6.45,245,1);
socket.emit("1",6.8,245,1);socket.emit("1",2.645,245,1);socket.emit("1",2.99,245,1);socket.emit("1",4.72,130,1);socket.emit("1",5.24,130,1);
socket.emit("1",1.1,130,1);socket.emit("1",1.575,130,1);socket.emit("1",2.045,130,1);socket.emit("1",4.2,130,1);socket.emit("1",5.45,185,1);
socket.emit("1",6.625,193,1);socket.emit("1",6.95,187,1);socket.emit("1",7.275,189,1);socket.emit("1",2.17,187,1);socket.emit("1",2.4925,187,1);
socket.emit("1",2.81,193,1);socket.emit("1",4,185,1);socket.emit("1",4.72,212.5,1);socket.emit("1",4.96,245,1);socket.emit("1",5.46,245,1);
socket.emit("1",7.378,245,1);socket.emit("1",7.628,245,1);socket.emit("1",7.878,245,1);socket.emit("1",8.128,245,1);socket.emit("1",2.0975,245,1);
socket.emit("1",3.975,245,1);socket.emit("1",4.475,245,1);socket.emit("1",2.375,245,1);socket.emit("1",6.05,245,1);socket.emit("1",7.1,245,1);
socket.emit("1",3.385,245,1);socket.emit("1",5.21,245,1);socket.emit("1",5.71,245,1);socket.emit("1",3.725,245,1);socket.emit("1",4.225,245,1);
socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);
socket.emit("1",8.86,311,1);socket.emit("1",9.06,311,1);socket.emit("1",9.26,311,1);socket.emit("1",9.46,311,1);socket.emit("1",9.66,311,1);
socket.emit("1",9.86,311,1);socket.emit("1",10.28,311,1);socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);
socket.emit("1",11.30,311,1);socket.emit("1",11.72,311,1);socket.emit("1",12.14,311,1);socket.emit("1",12.34,311,1);socket.emit("1",12.54,311,1);
socket.emit("1",12.74,311,1);socket.emit("1",12.94,311,1);socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);
socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);socket.emit("1",10.07,311,1);socket.emit("1",10.49,311,1);socket.emit("1",11.51,311,1);
socket.emit("1",11.93,311,1);
    }
     if (a.keyCode == 119) {//Defend Full Gens Base
socket.emit("1",4.73,245,1);socket.emit("1",5.0025,245,1);socket.emit("1",5.275,245,1);socket.emit("1",5.5475,245,1);socket.emit("1",5.82,245,1);
socket.emit("1",6.0925,245,1);socket.emit("1",6.365,245,1);socket.emit("1",6.6375,245,1);socket.emit("1",6.91,245,1);socket.emit("1",7.1825,245,1);
socket.emit("1",7.455,245,1);socket.emit("1",7.7275,245,1);socket.emit("1",8.0025,245,1);socket.emit("1",8.275,245,1);socket.emit("1",8.5475,245,1);
socket.emit("1",8.82,245,1);socket.emit("1",9.0925,245,1);socket.emit("1",9.3675,245,1);socket.emit("1",9.64,245,1);socket.emit("1",9.9125,245,1);
socket.emit("1",10.1875,245,1);socket.emit("1",10.4625,245,1);socket.emit("1",10.7375,245,1);socket.emit("1",5.999,180,1);socket.emit("1",6.275,130,1);
socket.emit("1",6.51,185,1);socket.emit("1",6.775,130,1);socket.emit("1",7.05,185,1);socket.emit("1",7.3,130,1);socket.emit("1",7.6,185,1);
socket.emit("1",7.85,130,1);socket.emit("1",8.15,185,1);socket.emit("1",8.4,130,1);socket.emit("1",8.675,185,1);socket.emit("1",8.925,130,1);
socket.emit("1",9.225,185,1);socket.emit("1",9.5,130,1);socket.emit("1",9.78,185,1);socket.emit("1",10.05,130,1);socket.emit("1",10.325,185,1);
socket.emit("1",10.6,130,1);socket.emit("1",4.5889,186.5,1);socket.emit("1",4.81,130,1);socket.emit("1",5.085,180.5,1);socket.emit("1",5.36,130,1);
socket.emit("1",5.64,180,1);socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);
socket.emit("1",8.66,311,1);socket.emit("1",8.86,311,1);socket.emit("1",9.07,311,1);socket.emit("1",9.28,311,1);socket.emit("1",9.48,311,1);
socket.emit("1",9.68,311,1);socket.emit("1",9.89,311,1);socket.emit("1",10.10,311,1);socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);
socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);
socket.emit("1",11.70,311,1);socket.emit("1",11.90,311,1);socket.emit("1",12.11,311,1);socket.emit("1",12.32,311,1);socket.emit("1",12.52,311,1);
socket.emit("1",12.72,311,1);socket.emit("1",12.93,311,1);socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);
socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);
     }
    if (a.keyCode == 120) {//Defend Full Houses Base
socket.emit("1",4.725,130,1);socket.emit("1",5.245,130,1);socket.emit("1",5.715,130,1);socket.emit("1",6.185,130,1);socket.emit("1",6.655,130,1);
socket.emit("1",7.13,130,1);socket.emit("1",7.6,130,1);socket.emit("1",1.85,130,1);socket.emit("1",2.32,130,1);socket.emit("1",2.79,130,1);
socket.emit("1",3.265,130,1);socket.emit("1",3.735,130,1);socket.emit("1",4.205,130,1);socket.emit("1",4.725,190,1);socket.emit("1",5.06,185,1);
socket.emit("1",5.4,185,1);socket.emit("1",5.725,190,1);socket.emit("1",6.045,186,1);socket.emit("1",6.374,185,1);socket.emit("1",6.7215,189.5,1);
socket.emit("1",7.0425,188.5,1);socket.emit("1",7.365,185,1);socket.emit("1",7.712,187.45,1);socket.emit("1",8.035,188.5,1);socket.emit("1",8.36,185,1);
socket.emit("1",2.425,188,1);socket.emit("1",2.75,190,1);socket.emit("1",3.075,184,1);socket.emit("1",3.42,186,1);socket.emit("1",3.74,190,1);
socket.emit("1",4.06,186,1);socket.emit("1",4.39,185,1);socket.emit("1",4.8625,245,1);socket.emit("1",5.1125,245,1);socket.emit("1",5.3625,245,1);
socket.emit("1",5.6125,245,1);socket.emit("1",5.8625,245,1);socket.emit("1",6.1125,245,1);socket.emit("1",6.3625,245,1);socket.emit("1",6.6125,245,1);
socket.emit("1",6.8625,245,1);socket.emit("1",7.14,245,1);socket.emit("1",7.39,245,1);socket.emit("1",7.64,246,1);socket.emit("1",7.89,246,1);
socket.emit("1",8.14,246,1);socket.emit("1",8.39,246,1);socket.emit("1",8.635,246,1);socket.emit("1",8.885,246,1);socket.emit("1",2.5825,245,1);
socket.emit("1",2.8625,245,1);socket.emit("1",3.1125,245,1);socket.emit("1",3.3625,245,1);socket.emit("1",3.6125,245,1);socket.emit("1",3.8625,245,1);
socket.emit("1",4.1125,245,1);socket.emit("1",4.3625,245,1);socket.emit("1",4.6125,245,1);socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);
socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);socket.emit("1",8.86,311,1);socket.emit("1",9.28,311,1);
socket.emit("1",9.48,311,1);socket.emit("1",9.68,311,1);socket.emit("1",10.10,311,1);socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);
socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);
socket.emit("1",11.70,311,1);socket.emit("1",11.90,311,1);socket.emit("1",12.32,311,1);socket.emit("1",12.52,311,1);socket.emit("1",12.72,311,1);
socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);
socket.emit("1",9.07,311,1);socket.emit("1",9.89,311,1);socket.emit("1",12.11,311,1);socket.emit("1",12.93,311,1);
    }
    if (a.keyCode == 121) {//Defend Full HousesandTurrets
socket.emit("1",4.725,130,1);socket.emit("1",3.985,183,1);socket.emit("1",5.475,183,1);socket.emit("1",6.47,184,1);socket.emit("1",7.85,186,1);
socket.emit("1",9.26,183,1);socket.emit("1",5.245,130,1);socket.emit("1",5.725,130,1);socket.emit("1",6.205,130,1);socket.emit("1",6.675,130,1);
socket.emit("1",7.145,130,1);socket.emit("1",7.615,130,1);socket.emit("1",8.085,130,1);socket.emit("1",8.555,130,1);socket.emit("1",9.025,130,1);
socket.emit("1",3.225,130,1);socket.emit("1",9.975,130,1);socket.emit("1",10.485,130,1);socket.emit("1",4.72,210,1);socket.emit("1",5.06,185,1);
socket.emit("1",5.81,189,1);socket.emit("1",6.13,190,1);socket.emit("1",6.81,187,1);socket.emit("1",7.13,191,1);socket.emit("1",7.45,185,1);
socket.emit("1",8.25,185,1);socket.emit("1",8.6,190,1);socket.emit("1",8.92,189,1);socket.emit("1",9.6,189,1);socket.emit("1",9.925,190,1);
socket.emit("1",4.39,185,1);socket.emit("1",4.94,246,1);socket.emit("1",5.1875,246,1);socket.emit("1",5.435,246,1);socket.emit("1",5.685,246,1);
socket.emit("1",5.935,246,1);socket.emit("1",6.24,246,1);socket.emit("1",6.49,246,1);socket.emit("1",6.74,246,1);socket.emit("1",6.99,246,1);
socket.emit("1",7.25,246,1);socket.emit("1",7.5,246,1);socket.emit("1",7.75,246,1);socket.emit("1",8,246,1);socket.emit("1",8.25,246,1);
socket.emit("1",8.5,246,1);socket.emit("1",8.75,246,1);socket.emit("1",9.01,246,1);socket.emit("1",9.26,246,1);socket.emit("1",9.51,246,1);
socket.emit("1",9.76,246,1);socket.emit("1",10.03,246,1);socket.emit("1",4,246,1);socket.emit("1",4.25,246,1);socket.emit("1",4.5,246,1);
socket.emit("1",7.86,311,1);socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);
socket.emit("1",8.86,311,1);socket.emit("1",9.28,311,1);socket.emit("1",9.48,311,1);socket.emit("1",9.68,311,1);socket.emit("1",10.10,311,1);
socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);socket.emit("1",11.10,311,1);
socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);socket.emit("1",11.70,311,1);socket.emit("1",11.90,311,1);socket.emit("1",12.32,311,1);
socket.emit("1",12.52,311,1);socket.emit("1",12.72,311,1);socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);
socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);socket.emit("1",9.07,311,1);socket.emit("1",9.89,311,1);socket.emit("1",12.11,311,1);
socket.emit("1",12.93,311,1);
    }
    if (a.keyCode == 115) {//Defend Full Defense2
socket.emit("1",5.065,188,1);socket.emit("1",5.426,185,1);socket.emit("1",6.1375,192,1);socket.emit("1",6.48,185,1);socket.emit("1",7.175,192,1);
socket.emit("1",7.525,190,1);socket.emit("1",1.93,191,1);socket.emit("1",2.28,192,1);socket.emit("1",2.965,187,1);socket.emit("1",3.305,192,1);
socket.emit("1",4.01,182,1);socket.emit("1",4.365,190,1);socket.emit("1",4.9,245.5,1);socket.emit("1",5.25,245.5,1);socket.emit("1",5.6,245.5,1);
socket.emit("1",5.95,245.5,1);socket.emit("1",6.35,245.5,1);socket.emit("1",6.65,245.5,1);socket.emit("1",7,245.5,1);socket.emit("1",7.35,245.5,1);
socket.emit("1",7.7,245.5,1);socket.emit("1",1.75,245.5,1);socket.emit("1",2.1,245.5,1);socket.emit("1",2.475,245.5,1);socket.emit("1",2.8,245.5,1);
socket.emit("1",3.11,245.5,1);socket.emit("1",3.49,245.5,1);socket.emit("1",3.85,245.5,1);socket.emit("1",4.15,245.5,1);socket.emit("1",4.55,245.5,1);
socket.emit("1",4.72,130,1);socket.emit("1",5.21,130,1);socket.emit("1",5.70,130,1);socket.emit("1",6.19,130,1);socket.emit("1",6.68,130,1);
socket.emit("1",7.17,130,1);socket.emit("1",7.65,130,1);socket.emit("1",8.13,130,1);socket.emit("1",8.61,130,1);socket.emit("1",9.09,130,1);
socket.emit("1",9.57,130,1);socket.emit("1",10.05,130,1);socket.emit("1",10.53,130,1);socket.emit("1",5.775,192,1);socket.emit("1",6.825,190,1);
socket.emit("1",1.585,183,1);socket.emit("1",2.619,186,1);socket.emit("1",3.6675,191,1);socket.emit("1",4.725,192,1);socket.emit("1",7.86,311,1);
socket.emit("1",8.06,311,1);socket.emit("1",8.26,311,1);socket.emit("1",8.46,311,1);socket.emit("1",8.66,311,1);socket.emit("1",8.86,311,1);
socket.emit("1",9.07,311,1);socket.emit("1",9.28,311,1);socket.emit("1",9.48,311,1);socket.emit("1",9.68,311,1);socket.emit("1",9.89,311,1);
socket.emit("1",10.10,311,1);socket.emit("1",10.30,311,1);socket.emit("1",10.50,311,1);socket.emit("1",10.70,311,1);socket.emit("1",10.90,311,1);
socket.emit("1",11.10,311,1);socket.emit("1",11.30,311,1);socket.emit("1",11.50,311,1);socket.emit("1",11.70,311,1);socket.emit("1",11.90,311,1);
socket.emit("1",12.11,311,1);socket.emit("1",12.32,311,1);socket.emit("1",12.52,311,1);socket.emit("1",12.72,311,1);socket.emit("1",12.93,311,1);
socket.emit("1",13.14,311,1);socket.emit("1",13.34,311,1);socket.emit("1",13.54,311,1);socket.emit("1",13.74,311,1);socket.emit("1",13.94,311,1);
    }
});
