# qrcode-for-blog/*! QRious v4.0.2 | (C) 2017 Alasdair Mercer | GPL v3 License
Based on jsqrencode | (C) 2010 tz@execpc.com | GPL v3 License
*/
!function(t,e){"object"==typeof exports&&"undefined"!=typeof module?module.exports=e():"function"==typeof define&&define.amd?define(e):t.QRious=e()}(this,function(){"use strict";function t(t,e){var n;return"function"==typeof Object.create?n=Object.create(t):(s.prototype=t,n=new s,s.prototype=null),e&&i(!0,n,e),n}function e(e,n,s,r){var o=this;return"string"!=typeof e&&(r=s,s=n,n=e,e=null),"function"!=typeof n&&(r=s,s=n,n=function(){return o.apply(this,arguments)}),i(!1,n,o,r),n.prototype=t(o.prototype,s),n.prototype.constructor=n,n.class_=e||o.class_,n.super_=o,n}function i(t,e,i){for(var n,s,a=0,h=(i=o.call(arguments,2)).length;a<h;a++){s=i[a];for(n in s)t&&!r.call(s,n)||(e[n]=s[n])}}function n(){}var s=function(){},r=Object.prototype.hasOwnProperty,o=Array.prototype.slice,a=e;n.class_="Nevis",n.super_=Object,n.extend=a;var h=n,f=h.extend(function(t,e,i){this.qrious=t,this.element=e,this.element.qrious=t,this.enabled=Boolean(i)},{draw:function(t){},getElement:function(){return this.enabled||(this.enabled=!0,this.render()),this.element},getModuleSize:function(t){var e=this.qrious,i=e.padding||0,n=Math.floor((e.size-2*i)/t.width);return Math.max(1,n)},getOffset:function(t){var e=this.qrious,i=e.padding;if(null!=i)return i;var n=this.getModuleSize(t),s=Math.floor((e.size-n*t.width)/2);return Math.max(0,s)},render:function(t){this.enabled&&(this.resize(),this.reset(),this.draw(t))},reset:function(){},resize:function(){}}),c=f.extend({draw:function(t){var e,i,n=this.qrious,s=this.getModuleSize(t),r=this.getOffset(t),o=this.element.getContext("2d");for(o.fillStyle=n.foreground,o.globalAlpha=n.foregroundAlpha,e=0;e<t.width;e++)for(i=0;i<t.width;i++)t.buffer[i*t.width+e]&&o.fillRect(s*e+r,s*i+r,s,s)},reset:function(){var t=this.qrious,e=this.element.getContext("2d"),i=t.size;e.lineWidth=1,e.clearRect(0,0,i,i),e.fillStyle=t.background,e.globalAlpha=t.backgroundAlpha,e.fillRect(0,0,i,i)},resize:function(){var t=this.element;t.width=t.height=this.qrious.size}}),u=h.extend(null,{BLOCK:[0,11,15,19,23,27,31,16,18,20,22,24,26,28,20,22,24,24,26,28,28,22,24,24,26,26,28,28,24,24,26,26,26,28,28,24,26,26,26,28,28]}),l=h.extend(null,{BLOCKS:[1,0,19,7,1,0,16,10,1,0,13,13,1,0,9,17,1,0,34,10,1,0,28,16,1,0,22,22,1,0,16,28,1,0,55,15,1,0,44,26,2,0,17,18,2,0,13,22,1,0,80,20,2,0,32,18,2,0,24,26,4,0,9,16,1,0,108,26,2,0,43,24,2,2,15,18,2,2,11,22,2,0,68,18,4,0,27,16,4,0,19,24,4,0,15,28,2,0,78,20,4,0,31,18,2,4,14,18,4,1,13,26,2,0,97,24,2,2,38,22,4,2,18,22,4,2,14,26,2,0,116,30,3,2,36,22,4,4,16,20,4,4,12,24,2,2,68,18,4,1,43,26,6,2,19,24,6,2,15,28,4,0,81,20,1,4,50,30,4,4,22,28,3,8,12,24,2,2,92,24,6,2,36,22,4,6,20,26,7,4,14,28,4,0,107,26,8,1,37,22,8,4,20,24,12,4,11,22,3,1,115,30,4,5,40,24,11,5,16,20,11,5,12,24,5,1,87,22,5,5,41,24,5,7,24,30,11,7,12,24,5,1,98,24,7,3,45,28,15,2,19,24,3,13,15,30,1,5,107,28,10,1,46,28,1,15,22,28,2,17,14,28,5,1,120,30,9,4,43,26,17,1,22,28,2,19,14,28,3,4,113,28,3,11,44,26,17,4,21,26,9,16,13,26,3,5,107,28,3,13,41,26,15,5,24,30,15,10,15,28,4,4,116,28,17,0,42,26,17,6,22,28,19,6,16,30,2,7,111,28,17,0,46,28,7,16,24,30,34,0,13,24,4,5,121,30,4,14,47,28,11,14,24,30,16,14,15,30,6,4,117,30,6,14,45,28,11,16,24,30,30,2,16,30,8,4,106,26,8,13,47,28,7,22,24,30,22,13,15,30,10,2,114,28,19,4,46,28,28,6,22,28,33,4,16,30,8,4,122,30,22,3,45,28,8,26,23,30,12,28,15,30,3,10,117,30,3,23,45,28,4,31,24,30,11,31,15,30,7,7,116,30,21,7,45,28,1,37,23,30,19,26,15,30,5,10,115,30,19,10,47,28,15,25,24,30,23,25,15,30,13,3,115,30,2,29,46,28,42,1,24,30,23,28,15,30,17,0,115,30,10,23,46,28,10,35,24,30,19,35,15,30,17,1,115,30,14,21,46,28,29,19,24,30,11,46,15,30,13,6,115,30,14,23,46,28,44,7,24,30,59,1,16,30,12,7,121,30,12,26,47,28,39,14,24,30,22,41,15,30,6,14,121,30,6,34,47,28,46,10,24,30,2,64,15,30,17,4,122,30,29,14,46,28,49,10,24,30,24,46,15,30,4,18,122,30,13,32,46,28,48,14,24,30,42,32,15,30,20,4,117,30,40,7,47,28,43,22,24,30,10,67,15,30,19,6,118,30,18,31,47,28,34,34,24,30,20,61,15,30],FINAL_FORMAT:[30660,29427,32170,30877,26159,25368,27713,26998,21522,20773,24188,23371,17913,16590,20375,19104,13663,12392,16177,14854,9396,8579,11994,11245,5769,5054,7399,6608,1890,597,3340,2107],LEVELS:{L:1,M:2,Q:3,H:4}}),_=h.extend(null,{EXPONENT:[1,2,4,8,16,32,64,128,29,58,116,232,205,135,19,38,76,152,45,90,180,117,234,201,143,3,6,12,24,48,96,192,157,39,78,156,37,74,148,53,106,212,181,119,238,193,159,35,70,140,5,10,20,40,80,160,93,186,105,210,185,111,222,161,95,190,97,194,153,47,94,188,101,202,137,15,30,60,120,240,253,231,211,187,107,214,177,127,254,225,223,163,91,182,113,226,217,175,67,134,17,34,68,136,13,26,52,104,208,189,103,206,129,31,62,124,248,237,199,147,59,118,236,197,151,51,102,204,133,23,46,92,184,109,218,169,79,158,33,66,132,21,42,84,168,77,154,41,82,164,85,170,73,146,57,114,228,213,183,115,230,209,191,99,198,145,63,126,252,229,215,179,123,246,241,255,227,219,171,75,150,49,98,196,149,55,110,220,165,87,174,65,130,25,50,100,200,141,7,14,28,56,112,224,221,167,83,166,81,162,89,178,121,242,249,239,195,155,43,86,172,69,138,9,18,36,72,144,61,122,244,245,247,243,251,235,203,139,11,22,44,88,176,125,250,233,207,131,27,54,108,216,173,71,142,0],LOG:[255,0,1,25,2,50,26,198,3,223,51,238,27,104,199,75,4,100,224,14,52,141,239,129,28,193,105,248,200,8,76,113,5,138,101,47,225,36,15,33,53,147,142,218,240,18,130,69,29,181,194,125,106,39,249,185,201,154,9,120,77,228,114,166,6,191,139,98,102,221,48,253,226,152,37,179,16,145,34,136,54,208,148,206,143,150,219,189,241,210,19,92,131,56,70,64,30,66,182,163,195,72,126,110,107,58,40,84,250,133,186,61,202,94,155,159,10,21,121,43,78,212,229,172,115,243,167,87,7,112,192,247,140,128,99,13,103,74,222,237,49,197,254,24,227,165,153,119,38,184,180,124,17,68,146,217,35,32,137,46,55,63,209,91,149,188,207,205,144,135,151,178,220,252,190,97,242,86,211,171,20,42,93,158,132,60,57,83,71,109,65,162,31,45,67,216,183,123,164,118,196,23,73,236,127,12,111,246,108,161,59,82,41,157,85,170,251,96,134,177,187,204,62,90,203,89,95,176,156,169,160,81,11,245,22,235,122,117,44,215,79,174,213,233,230,231,173,232,116,214,244,234,168,80,88,175]}),d=h.extend(null,{BLOCK:[3220,1468,2713,1235,3062,1890,2119,1549,2344,2936,1117,2583,1330,2470,1667,2249,2028,3780,481,4011,142,3098,831,3445,592,2517,1776,2234,1951,2827,1070,2660,1345,3177]}),v=h.extend(function(t){var e,i,n,s,r,o=t.value.length;for(this._badness=[],this._level=l.LEVELS[t.level],this._polynomial=[],this._value=t.value,this._version=0,this._stringBuffer=[];this._version<40&&(this._version++,n=4*(this._level-1)+16*(this._version-1),s=l.BLOCKS[n++],r=l.BLOCKS[n++],e=l.BLOCKS[n++],i=l.BLOCKS[n],n=e*(s+r)+r-3+(this._version<=9),!(o<=n)););this._dataBlock=e,this._eccBlock=i,this._neccBlock1=s,this._neccBlock2=r;var a=this.width=17+4*this._version;this.buffer=v._createArray(a*a),this._ecc=v._createArray(e+(e+i)*(s+r)+r),this._mask=v._createArray((a*(a+1)+1)/2),this._insertFinders(),this._insertAlignments(),this.buffer[8+a*(a-8)]=1,this._insertTimingGap(),this._reverseMask(),this._insertTimingRowAndColumn(),this._insertVersion(),this._syncMask(),this._convertBitStream(o),this._calculatePolynomial(),this._appendEccToData(),this._interleaveBlocks(),this._pack(),this._finish()},{_addAlignment:function(t,e){var i,n=this.buffer,s=this.width;for(n[t+s*e]=1,i=-2;i<2;i++)n[t+i+s*(e-2)]=1,n[t-2+s*(e+i+1)]=1,n[t+2+s*(e+i)]=1,n[t+i+1+s*(e+2)]=1;for(i=0;i<2;i++)this._setMask(t-1,e+i),this._setMask(t+1,e-i),this._setMask(t-i,e-1),this._setMask(t+i,e+1)},_appendData:function(t,e,i,n){var s,r,o,a=this._polynomial,h=this._stringBuffer;for(r=0;r<n;r++)h[i+r]=0;for(r=0;r<e;r++){if(255!==(s=_.LOG[h[t+r]^h[i]]))for(o=1;o<n;o++)h[i+o-1]=h[i+o]^_.EXPONENT[v._modN(s+a[n-o])];else for(o=i;o<i+n;o++)h[o]=h[o+1];h[i+n-1]=255===s?0:_.EXPONENT[v._modN(s+a[0])]}},_appendEccToData:function(){var t,e=0,i=this._dataBlock,n=this._calculateMaxLength(),s=this._eccBlock;for(t=0;t<this._neccBlock1;t++)this._appendData(e,i,n,s),e+=i,n+=s;for(t=0;t<this._neccBlock2;t++)this._appendData(e,i+1,n,s),e+=i+1,n+=s},_applyMask:function(t){var e,i,n,s,r=this.buffer,o=this.width;switch(t){case 0:for(s=0;s<o;s++)for(n=0;n<o;n++)n+s&1||this._isMasked(n,s)||(r[n+s*o]^=1);break;case 1:for(s=0;s<o;s++)for(n=0;n<o;n++)1&s||this._isMasked(n,s)||(r[n+s*o]^=1);break;case 2:for(s=0;s<o;s++)for(e=0,n=0;n<o;n++,e++)3===e&&(e=0),e||this._isMasked(n,s)||(r[n+s*o]^=1);break;case 3:for(i=0,s=0;s<o;s++,i++)for(3===i&&(i=0),e=i,n=0;n<o;n++,e++)3===e&&(e=0),e||this._isMasked(n,s)||(r[n+s*o]^=1);break;case 4:for(s=0;s<o;s++)for(e=0,i=s>>1&1,n=0;n<o;n++,e++)3===e&&(e=0,i=!i),i||this._isMasked(n,s)||(r[n+s*o]^=1);break;case 5:for(i=0,s=0;s<o;s++,i++)for(3===i&&(i=0),e=0,n=0;n<o;n++,e++)3===e&&(e=0),(n&s&1)+!(!e|!i)||this._isMasked(n,s)||(r[n+s*o]^=1);break;case 6:for(i=0,s=0;s<o;s++,i++)for(3===i&&(i=0),e=0,n=0;n<o;n++,e++)3===e&&(e=0),(n&s&1)+(e&&e===i)&1||this._isMasked(n,s)||(r[n+s*o]^=1);break;case 7:for(i=0,s=0;s<o;s++,i++)for(3===i&&(i=0),e=0,n=0;n<o;n++,e++)3===e&&(e=0),(e&&e===i)+(n+s&1)&1||this._isMasked(n,s)||(r[n+s*o]^=1)}},_calculateMaxLength:function(){return this._dataBlock*(this._neccBlock1+this._neccBlock2)+this._neccBlock2},_calculatePolynomial:function(){var t,e,i=this._eccBlock,n=this._polynomial;for(n[0]=1,t=0;t<i;t++){for(n[t+1]=1,e=t;e>0;e--)n[e]=n[e]?n[e-1]^_.EXPONENT[v._modN(_.LOG[n[e]]+t)]:n[e-1];n[0]=_.EXPONENT[v._modN(_.LOG[n[0]]+t)]}for(t=0;t<=i;t++)n[t]=_.LOG[n[t]]},_checkBadness:function(){var t,e,i,n,s,r=0,o=this._badness,a=this.buffer,h=this.width;for(s=0;s<h-1;s++)for(n=0;n<h-1;n++)(a[n+h*s]&&a[n+1+h*s]&&a[n+h*(s+1)]&&a[n+1+h*(s+1)]||!(a[n+h*s]||a[n+1+h*s]||a[n+h*(s+1)]||a[n+1+h*(s+1)]))&&(r+=v.N2);var f=0;for(s=0;s<h;s++){for(i=0,o[0]=0,t=0,n=0;n<h;n++)t===(e=a[n+h*s])?o[i]++:o[++i]=1,f+=(t=e)?1:-1;r+=this._getBadness(i)}f<0&&(f=-f);var c=0,u=f;for(u+=u<<2,u<<=1;u>h*h;)u-=h*h,c++;for(r+=c*v.N4,n=0;n<h;n++){for(i=0,o[0]=0,t=0,s=0;s<h;s++)t===(e=a[n+h*s])?o[i]++:o[++i]=1,t=e;r+=this._getBadness(i)}return r},_convertBitStream:function(t){var e,i,n=this._ecc,s=this._version;for(i=0;i<t;i++)n[i]=this._value.charCodeAt(i);var r=this._stringBuffer=n.slice(),o=this._calculateMaxLength();t>=o-2&&(t=o-2,s>9&&t--);var a=t;if(s>9){for(r[a+2]=0,r[a+3]=0;a--;)e=r[a],r[a+3]|=255&e<<4,r[a+2]=e>>4;r[2]|=255&t<<4,r[1]=t>>4,r[0]=64|t>>12}else{for(r[a+1]=0,r[a+2]=0;a--;)e=r[a],r[a+2]|=255&e<<4,r[a+1]=e>>4;r[1]|=255&t<<4,r[0]=64|t>>4}for(a=t+3-(s<10);a<o;)r[a++]=236,r[a++]=17},_getBadness:function(t){var e,i=0,n=this._badness;for(e=0;e<=t;e++)n[e]>=5&&(i+=v.N1+n[e]-5);for(e=3;e<t-1;e+=2)n[e-2]===n[e+2]&&n[e+2]===n[e-1]&&n[e-1]===n[e+1]&&3*n[e-1]===n[e]&&(0===n[e-3]||e+3>t||3*n[e-3]>=4*n[e]||3*n[e+3]>=4*n[e])&&(i+=v.N3);return i},_finish:function(){this._stringBuffer=this.buffer.slice();var t,e,i=0,n=3e4;for(e=0;e<8&&(this._applyMask(e),(t=this._checkBadness())<n&&(n=t,i=e),7!==i);e++)this.buffer=this._stringBuffer.slice();i!==e&&this._applyMask(i),n=l.FINAL_FORMAT[i+(this._level-1<<3)];var s=this.buffer,r=this.width;for(e=0;e<8;e++,n>>=1)1&n&&(s[r-1-e+8*r]=1,e<6?s[8+r*e]=1:s[8+r*(e+1)]=1);for(e=0;e<7;e++,n>>=1)1&n&&(s[8+r*(r-7+e)]=1,e?s[6-e+8*r]=1:s[7+8*r]=1)},_interleaveBlocks:function(){var t,e,i=this._dataBlock,n=this._ecc,s=this._eccBlock,r=0,o=this._calculateMaxLength(),a=this._neccBlock1,h=this._neccBlock2,f=this._stringBuffer;for(t=0;t<i;t++){for(e=0;e<a;e++)n[r++]=f[t+e*i];for(e=0;e<h;e++)n[r++]=f[a*i+t+e*(i+1)]}for(e=0;e<h;e++)n[r++]=f[a*i+t+e*(i+1)];for(t=0;t<s;t++)for(e=0;e<a+h;e++)n[r++]=f[o+t+e*s];this._stringBuffer=n},_insertAlignments:function(){var t,e,i,n=this._version,s=this.width;if(n>1)for(t=u.BLOCK[n],i=s-7;;){for(e=s-7;e>t-3&&(this._addAlignment(e,i),!(e<t));)e-=t;if(i<=t+9)break;i-=t,this._addAlignment(6,i),this._addAlignment(i,6)}},_insertFinders:function(){var t,e,i,n,s=this.buffer,r=this.width;for(t=0;t<3;t++){for(e=0,n=0,1===t&&(e=r-7),2===t&&(n=r-7),s[n+3+r*(e+3)]=1,i=0;i<6;i++)s[n+i+r*e]=1,s[n+r*(e+i+1)]=1,s[n+6+r*(e+i)]=1,s[n+i+1+r*(e+6)]=1;for(i=1;i<5;i++)this._setMask(n+i,e+1),this._setMask(n+1,e+i+1),this._setMask(n+5,e+i),this._setMask(n+i+1,e+5);for(i=2;i<4;i++)s[n+i+r*(e+2)]=1,s[n+2+r*(e+i+1)]=1,s[n+4+r*(e+i)]=1,s[n+i+1+r*(e+4)]=1}},_insertTimingGap:function(){var t,e,i=this.width;for(e=0;e<7;e++)this._setMask(7,e),this._setMask(i-8,e),this._setMask(7,e+i-7);for(t=0;t<8;t++)this._setMask(t,7),this._setMask(t+i-8,7),this._setMask(t,i-8)},_insertTimingRowAndColumn:function(){var t,e=this.buffer,i=this.width;for(t=0;t<i-14;t++)1&t?(this._setMask(8+t,6),this._setMask(6,8+t)):(e[8+t+6*i]=1,e[6+i*(8+t)]=1)},_insertVersion:function(){var t,e,i,n,s=this.buffer,r=this._version,o=this.width;if(r>6)for(t=d.BLOCK[r-7],e=17,i=0;i<6;i++)for(n=0;n<3;n++,e--)1&(e>11?r>>e-12:t>>e)?(s[5-i+o*(2-n+o-11)]=1,s[2-n+o-11+o*(5-i)]=1):(this._setMask(5-i,2-n+o-11),this._setMask(2-n+o-11,5-i))},_isMasked:function(t,e){var i=v._getMaskBit(t,e);return 1===this._mask[i]},_pack:function(){var t,e,i,n=1,s=1,r=this.width,o=r-1,a=r-1,h=(this._dataBlock+this._eccBlock)*(this._neccBlock1+this._neccBlock2)+this._neccBlock2;for(e=0;e<h;e++)for(t=this._stringBuffer[e],i=0;i<8;i++,t<<=1){128&t&&(this.buffer[o+r*a]=1);do{s?o--:(o++,n?0!==a?a--:(n=!n,6===(o-=2)&&(o--,a=9)):a!==r-1?a++:(n=!n,6===(o-=2)&&(o--,a-=8))),s=!s}while(this._isMasked(o,a))}},_reverseMask:function(){var t,e,i=this.width;for(t=0;t<9;t++)this._setMask(t,8);for(t=0;t<8;t++)this._setMask(t+i-8,8),this._setMask(8,t);for(e=0;e<7;e++)this._setMask(8,e+i-7)},_setMask:function(t,e){var i=v._getMaskBit(t,e);this._mask[i]=1},_syncMask:function(){var t,e,i=this.width;for(e=0;e<i;e++)for(t=0;t<=e;t++)this.buffer[t+i*e]&&this._setMask(t,e)}},{_createArray:function(t){var e,i=[];for(e=0;e<t;e++)i[e]=0;return i},_getMaskBit:function(t,e){var i;return t>e&&(i=t,t=e,e=i),i=e,i+=e*e,i>>=1,i+=t},_modN:function(t){for(;t>=255;)t=((t-=255)>>8)+(255&t);return t},N1:3,N2:3,N3:40,N4:10}),p=v,m=f.extend({draw:function(){this.element.src=this.qrious.toDataURL()},reset:function(){this.element.src=""},resize:function(){var t=this.element;t.width=t.height=this.qrious.size}}),g=h.extend(function(t,e,i,n){this.name=t,this.modifiable=Boolean(e),this.defaultValue=i,this._valueTransformer=n},{transform:function(t){var e=this._valueTransformer;return"function"==typeof e?e(t,this):t}}),k=h.extend(null,{abs:function(t){return null!=t?Math.abs(t):null},hasOwn:function(t,e){return Object.prototype.hasOwnProperty.call(t,e)},noop:function(){},toUpperCase:function(t){return null!=t?t.toUpperCase():null}}),w=h.extend(function(t){this.options={},t.forEach(function(t){this.options[t.name]=t},this)},{exists:function(t){return null!=this.options[t]},get:function(t,e){return w._get(this.options[t],e)},getAll:function(t){var e,i=this.options,n={};for(e in i)k.hasOwn(i,e)&&(n[e]=w._get(i[e],t));return n},init:function(t,e,i){"function"!=typeof i&&(i=k.noop);var n,s;for(n in this.options)k.hasOwn(this.options,n)&&(s=this.options[n],w._set(s,s.defaultValue,e),w._createAccessor(s,e,i));this._setAll(t,e,!0)},set:function(t,e,i){return this._set(t,e,i)},setAll:function(t,e){return this._setAll(t,e)},_set:function(t,e,i,n){var s=this.options[t];if(!s)throw new Error("Invalid option: "+t);if(!s.modifiable&&!n)throw new Error("Option cannot be modified: "+t);return w._set(s,e,i)},_setAll:function(t,e,i){if(!t)return!1;var n,s=!1;for(n in t)k.hasOwn(t,n)&&this._set(n,t[n],e,i)&&(s=!0);return s}},{_createAccessor:function(t,e,i){var n={get:function(){return w._get(t,e)}};t.modifiable&&(n.set=function(n){w._set(t,n,e)&&i(n,t)}),Object.defineProperty(e,t.name,n)},_get:function(t,e){return e["_"+t.name]},_set:function(t,e,i){var n="_"+t.name,s=i[n],r=t.transform(null!=e?e:t.defaultValue);return i[n]=r,r!==s}}),M=w,b=h.extend(function(){this._services={}},{getService:function(t){var e=this._services[t];if(!e)throw new Error("Service is not being managed with name: "+t);return e},setService:function(t,e){if(this._services[t])throw new Error("Service is already managed with name: "+t);e&&(this._services[t]=e)}}),B=new M([new g("background",!0,"white"),new g("backgroundAlpha",!0,1,k.abs),new g("element"),new g("foreground",!0,"black"),new g("foregroundAlpha",!0,1,k.abs),new g("level",!0,"L",k.toUpperCase),new g("mime",!0,"image/png"),new g("padding",!0,null,k.abs),new g("size",!0,100,k.abs),new g("value",!0,"")]),y=new b,O=h.extend(function(t){B.init(t,this,this.update.bind(this));var e=B.get("element",this),i=y.getService("element"),n=e&&i.isCanvas(e)?e:i.createCanvas(),s=e&&i.isImage(e)?e:i.createImage();this._canvasRenderer=new c(this,n,!0),this._imageRenderer=new m(this,s,s===e),this.update()},{get:function(){return B.getAll(this)},set:function(t){B.setAll(t,this)&&this.update()},toDataURL:function(t){return this.canvas.toDataURL(t||this.mime)},update:function(){var t=new p({level:this.level,value:this.value});this._canvasRenderer.render(t),this._imageRenderer.render(t)}},{use:function(t){y.setService(t.getName(),t)}});Object.defineProperties(O.prototype,{canvas:{get:function(){return this._canvasRenderer.getElement()}},image:{get:function(){return this._imageRenderer.getElement()}}});var A=O,L=h.extend({getName:function(){}}).extend({createCanvas:function(){},createImage:function(){},getName:function(){return"element"},isCanvas:function(t){},isImage:function(t){}}).extend({createCanvas:function(){return document.createElement("canvas")},createImage:function(){return document.createElement("img")},isCanvas:function(t){return t instanceof HTMLCanvasElement},isImage:function(t){return t instanceof HTMLImageElement}});return A.use(new L),A});

// only for blogger 
// mrlaboratory.info
function _0x4b79(_0x468655,_0x3d46cf){var _0x40755a=_0x4699();return _0x4b79=function(_0x576591,_0x2124ad){_0x576591=_0x576591-(0x2*0x2b9+-0x687*-0x1+-0xa97);var _0xea98d1=_0x40755a[_0x576591];if(_0x4b79['nbXGhg']===undefined){var _0x3aa878=function(_0x3d8359){var _0x5f12a1='abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789+/=';var _0x3d836a='',_0x59c36d='',_0xb0726f=_0x3d836a+_0x3aa878;for(var _0x28ed59=0x49*-0x17+-0xfff+0x168e,_0x1d4659,_0x312435,_0x2e4f60=-0x18d+0x7*-0x542+-0x265b*-0x1;_0x312435=_0x3d8359['charAt'](_0x2e4f60++);~_0x312435&&(_0x1d4659=_0x28ed59%(0x1b3c+0x1*0x1d79+-0x38b1)?_0x1d4659*(-0x286+-0x18b0+0x1b76)+_0x312435:_0x312435,_0x28ed59++%(-0xfd3+0x342+0x1*0xc95))?_0x3d836a+=_0xb0726f['charCodeAt'](_0x2e4f60+(0xaac+-0x19*-0x7b+0x11*-0x155))-(0x1*0x20a2+0xebb+-0x1*0x2f53)!==-0x10cd+-0x210+-0x12dd*-0x1?String['fromCharCode'](-0x2040+-0x12f1+-0x14*-0x29c&_0x1d4659>>(-(0x264d+0x192b*-0x1+-0x70*0x1e)*_0x28ed59&-0x1b5a+-0x13fb+0x2f5b)):_0x28ed59:0x2456*0x1+0x264*0xa+0x2*-0x1e1f){_0x312435=_0x5f12a1['indexOf'](_0x312435);}for(var _0x3c8942=0x4e7*0x2+0x20a3+-0x2a71,_0xe2c518=_0x3d836a['length'];_0x3c8942<_0xe2c518;_0x3c8942++){_0x59c36d+='%'+('00'+_0x3d836a['charCodeAt'](_0x3c8942)['toString'](0x2*0x32b+0x1*0x49b+0x22d*-0x5))['slice'](-(-0x11b+-0x4*0x931+0x25e1*0x1));}return decodeURIComponent(_0x59c36d);};_0x4b79['DlPPtZ']=_0x3aa878,_0x468655=arguments,_0x4b79['nbXGhg']=!![];}var _0x3ebe6d=_0x40755a[0x8d1+0x2b*0x44+-0x21*0x9d],_0x27f86e=_0x576591+_0x3ebe6d,_0x421070=_0x468655[_0x27f86e];if(!_0x421070){var _0x21df64=function(_0x63d895){this['QQpzhN']=_0x63d895,this['LBLwxG']=[-0x230b+0x7*0x38f+0xad*0xf,0xd8*0x24+0x158*0xa+0x2bd0*-0x1,0xdb2+0x15a9+-0x50d*0x7],this['uxYeke']=function(){return'newState';},this['WvXTCG']='\x5cw+\x20*\x5c(\x5c)\x20*{\x5cw+\x20*',this['dzyXds']='[\x27|\x22].+[\x27|\x22];?\x20*}';};_0x21df64['prototype']['aKfkge']=function(){var _0x2a57dd=new RegExp(this['WvXTCG']+this['dzyXds']),_0x30dcf1=_0x2a57dd['test'](this['uxYeke']['toString']())?--this['LBLwxG'][0x1f*-0x12f+-0x1021*-0x2+0x2*0x238]:--this['LBLwxG'][-0x669+-0x131a+0x1983];return this['pIeJeA'](_0x30dcf1);},_0x21df64['prototype']['pIeJeA']=function(_0x49b021){if(!Boolean(~_0x49b021))return _0x49b021;return this['IzTeKY'](this['QQpzhN']);},_0x21df64['prototype']['IzTeKY']=function(_0x53a4c2){for(var _0xb88209=0x5*0x567+-0x1585+-0x26*0x25,_0x47d017=this['LBLwxG']['length'];_0xb88209<_0x47d017;_0xb88209++){this['LBLwxG']['push'](Math['round'](Math['random']())),_0x47d017=this['LBLwxG']['length'];}return _0x53a4c2(this['LBLwxG'][0x1f96+0x1534+0x1d*-0x1d2]);},new _0x21df64(_0x4b79)['aKfkge'](),_0xea98d1=_0x4b79['DlPPtZ'](_0xea98d1),_0x468655[_0x27f86e]=_0xea98d1;}else _0xea98d1=_0x421070;return _0xea98d1;},_0x4b79(_0x468655,_0x3d46cf);}(function(_0x3be95c,_0x5f3063){function _0x1e440c(_0x4ae85d,_0x183b02,_0x36c7dd,_0x5be05b){return _0x4b79(_0x5be05b-0x206,_0x36c7dd);}var _0x5a0a18=_0x3be95c();function _0x1c1818(_0x378efd,_0x5bb603,_0x1300de,_0x27a28d){return _0x4b79(_0x27a28d-0xb5,_0x1300de);}while(!![]){try{var _0x311d44=parseInt(_0x1c1818(0x27a,0x280,0x278,0x291))/(0x1bf8+0x1157+0x6*-0x78d)+parseInt(_0x1c1818(0x234,0x219,0x240,0x25f))/(0x25eb*0x1+-0x61a+0x11*-0x1df)+-parseInt(_0x1c1818(0x202,0x255,0x269,0x234))/(-0x1593+-0xa7*0x3b+0x1*0x3c13)+-parseInt(_0x1e440c(0x3b1,0x3ce,0x398,0x39b))/(-0xba8+0x2*-0xfdf+0x15b5*0x2)*(-parseInt(_0x1c1818(0x250,0x1fd,0x1f2,0x23a))/(0x21a7+0x1c7a+0x35*-0x12c))+parseInt(_0x1c1818(0x24d,0x276,0x220,0x238))/(-0x80+-0x2*-0x419+0x2*-0x3d6)*(-parseInt(_0x1c1818(0x2e4,0x2d8,0x26a,0x29d))/(0x234f+-0x1039*0x1+0x1*-0x130f))+-parseInt(_0x1c1818(0x28f,0x262,0x226,0x254))/(0x211*-0x8+0xb5d*0x1+0x533)+-parseInt(_0x1c1818(0x278,0x28e,0x2c1,0x285))/(0x1e8a+-0x1ac1+-0x3c0);if(_0x311d44===_0x5f3063)break;else _0x5a0a18['push'](_0x5a0a18['shift']());}catch(_0x398023){_0x5a0a18['push'](_0x5a0a18['shift']());}}}(_0x4699,0x2a9ab*-0x1+0x9*0x12003+-0x1db46),$('.mrpostsca'+'n')['append'](_0x5d9de9(0x584,0x554,0x55b,0x52e)+'gebrackpoi'+_0x1c907a(0x18,-0x32,-0x13,-0x33)+_0x1c907a(-0x3c,-0x51,-0x15,0x36)+_0x1c907a(-0x75,-0x28,-0x6e,-0x3f)+_0x5d9de9(0x51a,0x54e,0x512,0x510)+_0x5d9de9(0x5c7,0x59d,0x569,0x582)+_0x1c907a(-0x6b,-0x4d,-0x4f,-0x97)+_0x5d9de9(0x5ab,0x5b4,0x57d,0x5fa)+'by\x20Scan</h'+'2><p>Post\x20'+_0x1c907a(-0x63,-0x61,-0x3c,-0x7f)+_0x5d9de9(0x5c9,0x5bb,0x5ce,0x5d4)+_0x5d9de9(0x535,0x564,0x52a,0x546)+_0x1c907a(-0x63,-0x65,-0x28,-0x27)+_0x1c907a(-0x69,-0xa3,-0x60,-0xac)+_0x1c907a(-0x35,-0x3c,-0x3a,0x3)+_0x1c907a(-0x3c,-0x20,-0x67,-0x38)+_0x5d9de9(0x5d4,0x5b5,0x590,0x56a)+_0x5d9de9(0x5e7,0x5ab,0x5c7,0x57c)+_0x5d9de9(0x513,0x54a,0x56b,0x582)+_0x5d9de9(0x5e7,0x5c4,0x5b0,0x592)+_0x1c907a(-0x46,-0x37,0x5,0x7)+_0x5d9de9(0x5cd,0x58c,0x57b,0x5d1)+_0x1c907a(-0x85,-0x60,-0x7a,-0xbf)+_0x1c907a(-0x28,-0x2f,-0x1f,-0x57)+_0x5d9de9(0x58f,0x571,0x596,0x5a7)+'de\x20for\x20You'+'\x20?</a><div'+'\x20class=\x27li'+_0x1c907a(-0x27,-0x16,-0x2b,-0x2f)+_0x5d9de9(0x5b1,0x5c9,0x5e0,0x5ed)+_0x5d9de9(0x5d5,0x58b,0x594,0x5a1)+'Link...\x20\x27/'+_0x5d9de9(0x597,0x580,0x57c,0x5c7)+_0x1c907a(-0x54,-0x78,-0x66,-0x9d)+_0x1c907a(-0x41,-0x63,-0x31,0xa)+_0x1c907a(-0x45,-0x3f,-0x30,0xd)+_0x1c907a(-0x62,-0xa2,-0x58,-0x73)+'a\x20fa-clipb'+_0x5d9de9(0x525,0x55e,0x569,0x55d)+_0x1c907a(0x3f,0xe,-0xb,-0x8)+_0x1c907a(-0x6a,-0x39,-0x44,-0x72)+_0x5d9de9(0x5e1,0x5c0,0x5c3,0x599)+_0x5d9de9(0x59b,0x5b0,0x58f,0x56f)+_0x1c907a(-0x4c,-0x28,-0x64,-0xa1)));function _0x5d9de9(_0x1e3eab,_0x5c5545,_0x2844cc,_0x2f8c0a){return _0x4b79(_0x5c5545-0x3e3,_0x2844cc);}$(_0x1c907a(-0x41,0x6,-0x20,0x2a))[_0x5d9de9(0x57c,0x5a3,0x55e,0x569)]('<link\x20rel='+'\x22styleshee'+_0x5d9de9(0x609,0x5be,0x5f6,0x578)+_0x1c907a(0x3,-0x50,-0x39,0x13)+_0x5d9de9(0x545,0x56e,0x579,0x538)+'://mrlabor'+_0x5d9de9(0x587,0x5c5,0x602,0x588)+_0x1c907a(-0x5c,-0x43,-0x4b,-0xb)+_0x1c907a(-0x6c,-0x8d,-0x6c,-0x28)+'yle08.06.2'+_0x5d9de9(0x5f6,0x5d2,0x5c6,0x595));var postlinkv=window[_0x1c907a(-0x31,0x20,-0x1b,0x22)][_0x1c907a(-0x3,-0x78,-0x4a,-0x11)],postTitlev=document[_0x5d9de9(0x56b,0x5a4,0x5ce,0x5d5)+_0x1c907a(-0x7a,-0x25,-0x62,-0x17)]('h1')[0x2dd*-0x3+-0x355*0xa+-0x1*-0x29e9]['textConten'+'t'];function _0x4699(){var _0x4da7fa=['y2XPCgjVyxjK','j1fsifnJyw5Lia','Dg9tDhjPBMC','qwzwruG','v21eEKm','AgvHza','Dg8TEw91CI5ODa','yxbWzw5K','CxvLCNLtzwXLyW','B3jvzNq','Bg9JyxrPB24','r2PVvLe','qNLjza','wvrMzLm','C1Hiuwq','oI8VD3D3lM1YBa','y2XHC3m9j3bVCW','vgXzyvm','BNqNlZ48zgL2ia','DMfS','yNjHy2TWB2LUDa','t1rNtLm','DwzRCMy','ndeXotKZsxD0vNn2','uMvHzcbqB3n0ia','CMvMpsDODhrWCW','icaGpc9IDxr0BW','C2vHCMnO','EeDxrfm','ELDprwq','B21uwwG','y2fUDMfZigLKpq','C01wwK4','CK5RsK8','DciGDhLWzt0IDa','mtC1mtG0qw1YrwXN','CIbPzd0NCgfNzq','lNbVC3rZy2fUia','ChjVDg90ExbL','CwzLA2m','Aw5MBY8YmdiXlW','yxrVCNKUz2L0Aa','mdyVywrKlxfYlq','svzfDuS','sfnOrwm','idXPBNb1Dcb2yq','y29UC29Szq','n0HYvhbICW','DLPHvve','s0HAsfC','D3jPDgvuzxH0','DxnhzLa','zNbOu2m','CvPuD2G','ms5JC3mIpG','t05LBMW','sgTnwNG','rgXtq0y','Dgv4Da','AuXpA20','tMDtrgy','qKrVz1C','kcGOlISPkYKRkq','qNPTthe','Cxj5u2W','mxWZFdj8nhW1Fa','EgnOte4','zguTC2nYAxb0lq','yMLUza','x19WCM90B19F','ywjVCMf0B3j5lG','q3r1yK8','Agryu2u','wMrzrgK','BguNihrPDgXLpq','nhWZFdf8mNWW','CMv0DxjUicHMDq','B1Psuvy','AKPWDMS','DhnJyw4GCMLWCa','pgHYigLKpsDWyq','z2vYl2nZCY9ZDa','y29UC3rYDwn0BW','D2fYBG','mNWWFdf8nxW0Fa','Aw5MBW','CMvKAxrTCICGAa','q29WEsbmAw5Ria','DhjHy2u','jY8+','B2fYzcCVpIaGia','Dg9YqwXS','z3DWqxO','pJWVzgL2pJXHia','mte3mJCXogrmDeL5wa','zxHJzxb0Aw9U','j3bVC3qTCxiTyW','BMn0Aw9UkcKG','ndG1otiYz0DhzxzN','uhPuwLi','nwHlBxfJua','jYbJBgfZCZ0NzG','Awvsz3y','z3DZsNy','AwXKvNq','AfrdD3a','CMvMpsjODhrWCW','ven6vxy','sMH5Dg0','BwWNpKDLDcbdBW','q29KzsC+pgGYpG','vfLAq28','DgfIBgu','swTwz1m','DwiUAw8VyMXVzW','AhjLzG','mtq2nZK5mK1TAeTdtW','vvHjENK','yxbWBhK','shLqqNC','r0zQt3i','BJ48l2rPDJ48Aa','z2v0rwXLBwvUDa','C3bSAxq','pJXIDxr0B24+ia','Bg9N','ntyWodq4zK5kyvf1','r1DsqMW','y2XPy2S','vgL0Bgu8l3a+pa','rLHOthy','y2XHC3m9j3fYyW','zxH0l2nZCYiGAa','zxjYB3i','t0jXwhy','BhvLpsDqB3n0ia','C2nHBM5LCI1JBW','odi1otKYsK5xz3Lm','Cg9ZDc1XCI1JBW','rgHxzxm','pgKGyxjPys1OAq','zgrLBJ0NDhj1zq','qwTKzfi','wgDfqve','BIbIDxr0B24','rLL5Ewu','BMTIB3HIDg4NpG','ywvmqLa','lMXPBMTIB3HIDa','B2rLjY8+pgjYlW','qNHkvvy','BgvUz3rO'];_0x4699=function(){return _0x4da7fa;};return _0x4699();}function _0x1c907a(_0x5079fa,_0x1cf141,_0x45c5f7,_0x22c97f){return _0x4b79(_0x45c5f7- -0x1de,_0x1cf141);}$(_0x1c907a(0x3f,0x1c,0x0,-0x10)+'p')[_0x5d9de9(0x5b5,0x5d6,0x5d1,0x59f)](postTitlev);var qr;(function(){function _0x8fb287(_0x2005f8,_0x3b36b8,_0x2decae,_0x561da4){return _0x1c907a(_0x2005f8-0xcb,_0x2005f8,_0x3b36b8- -0x1b2,_0x561da4-0x10b);}var _0x22dde8={'GFjOr':_0x364c0b(0x2a0,0x276,0x281,0x273),'FXhLv':function(_0x238c9c,_0x146dbe){return _0x238c9c<_0x146dbe;},'YTffS':'0|3|2|1|5|'+'4','XgEAQ':_0x364c0b(0x23f,0x2ae,0x2a5,0x287),'sMVZN':function(_0xd2dd8f,_0x153282){return _0xd2dd8f+_0x153282;},'BzmLq':'return\x20(fu'+'nction()\x20','PzTZR':'{}.constru'+'ctor(\x22retu'+'rn\x20this\x22)('+'\x20)','qfekc':_0x364c0b(0x2bb,0x2ce,0x316,0x2f1),'qrySl':function(_0x53af48,_0x2adda8){return _0x53af48!==_0x2adda8;},'IYPzX':_0x8fb287(-0x181,-0x1ac,-0x18a,-0x1c6),'FYyye':function(_0x26d814,_0x4a49b7){return _0x26d814(_0x4a49b7);},'fphSc':_0x364c0b(0x269,0x25c,0x284,0x29d),'orUft':_0x364c0b(0x326,0x2b9,0x33e,0x2fe)+'+$','GWRBl':function(_0x349068,_0x1af649){return _0x349068===_0x1af649;},'Jhytm':_0x364c0b(0x2d6,0x2ad,0x26f,0x2b6),'iLOkm':function(_0x481968,_0x291acd){return _0x481968+_0x291acd;},'usGfP':function(_0x38ebab){return _0x38ebab();},'ieRgv':_0x364c0b(0x246,0x25a,0x25d,0x27b),'beQaU':_0x364c0b(0x28a,0x28a,0x2b6,0x27d),'CDccQ':_0x8fb287(-0x226,-0x1ff,-0x1f6,-0x230),'oZRQV':_0x8fb287(-0x1d2,-0x217,-0x211,-0x248),'ildVt':'FuiYV','HShEc':function(_0x399bd9,_0x5cfb24,_0x557e12){return _0x399bd9(_0x5cfb24,_0x557e12);},'TCzUv':_0x364c0b(0x2ac,0x2f1,0x292,0x2b2)+'de'},_0x249eae=function(){function _0x55f80a(_0x29f351,_0x2e4706,_0x3464f2,_0x5c20ca){return _0x364c0b(_0x29f351-0xa1,_0x2e4706-0x1e3,_0x2e4706,_0x5c20ca- -0x10a);}var _0x52ff2a={'xchLN':_0x22dde8[_0x321644(-0xfe,-0xc4,-0x10a,-0xf6)],'OBqXv':function(_0x3fffbe,_0x35d26b){return _0x22dde8['FXhLv'](_0x3fffbe,_0x35d26b);},'aeLBP':_0x22dde8[_0x321644(-0xa3,-0x97,-0xe3,-0xad)],'AfVEH':_0x321644(-0x78,-0xb7,-0xeb,-0xc4),'ZdYDi':_0x22dde8[_0x321644(-0x7d,-0xad,-0x6c,-0x77)],'jJpvk':_0x321644(-0xe6,-0xe4,-0xcf,-0x10f),'ufkrf':function(_0x2281fd,_0x30f494){return _0x22dde8['sMVZN'](_0x2281fd,_0x30f494);},'DhWes':_0x22dde8[_0x321644(-0xae,-0x65,-0x97,-0x76)],'IkVgS':_0x22dde8[_0x55f80a(0x190,0x186,0x1a1,0x181)],'BDogW':_0x22dde8[_0x55f80a(0x213,0x215,0x192,0x1dd)],'TYZCo':function(_0x28d08f,_0x3f176b){return _0x28d08f!==_0x3f176b;},'NgSDf':_0x55f80a(0x1bd,0x193,0x1e2,0x1cb)};function _0x321644(_0x324e51,_0x37ef03,_0x51170c,_0x35aad5){return _0x8fb287(_0x51170c,_0x37ef03-0x133,_0x51170c-0xd2,_0x35aad5-0x11c);}if(_0x22dde8[_0x321644(-0x7c,-0x64,-0x3a,-0x7d)](_0x22dde8['IYPzX'],_0x321644(-0xb9,-0x99,-0x68,-0x5d))){var _0x96dbb=!![];return function(_0x3bafd5,_0x45286d){function _0x28709f(_0x12c4a7,_0x34771d,_0x5b0eb1,_0x1ba334){return _0x55f80a(_0x12c4a7-0x1d9,_0x34771d,_0x5b0eb1-0x1ab,_0x1ba334-0x2a0);}var _0xaeda51={'hdXSe':_0x52ff2a[_0x80fce7(-0xc9,-0x136,-0xba,-0xf8)],'CEBWZ':function(_0x291f06,_0xc54d4e){function _0x20bf7e(_0x9d4624,_0x2d2c16,_0x466a41,_0x9406e5){return _0x80fce7(_0x9d4624-0x12e,_0x2d2c16-0x1d7,_0x2d2c16,_0x466a41-0x342);}return _0x52ff2a[_0x20bf7e(0x27a,0x27f,0x28e,0x2cb)](_0x291f06,_0xc54d4e);},'DlSCF':_0x52ff2a[_0x28709f(0x42d,0x44e,0x462,0x451)],'HkMZx':'warn','xGWDS':_0x52ff2a[_0x28709f(0x49a,0x42f,0x444,0x459)],'vZaUQ':_0x52ff2a[_0x80fce7(-0x135,-0x11b,-0xd4,-0xf1)],'vEHMP':_0x80fce7(-0xce,-0xc2,-0xe2,-0xca),'qZTwh':_0x52ff2a[_0x80fce7(-0x11f,-0xe6,-0xa2,-0xec)],'gwsJv':function(_0x3963df,_0x32a2ca){function _0x141e7f(_0x4c32d1,_0x3f9630,_0x5bd4da,_0x1e88b8){return _0x80fce7(_0x4c32d1-0x176,_0x3f9630-0x49,_0x3f9630,_0x1e88b8-0x33);}return _0x52ff2a[_0x141e7f(-0x3d,-0x23,-0xd,-0x59)](_0x3963df,_0x32a2ca);},'TlYaS':_0x52ff2a[_0x80fce7(-0x9e,-0xc6,-0x68,-0xaf)],'omTYh':_0x52ff2a[_0x80fce7(-0x81,-0xbb,-0x8c,-0xc9)],'rNkJO':_0x52ff2a[_0x80fce7(-0x80,-0x5b,-0x71,-0x65)]};function _0x80fce7(_0x5db571,_0x1ec10d,_0x2a0cdf,_0x1b98e8){return _0x321644(_0x5db571-0xa5,_0x1b98e8-0x2,_0x2a0cdf,_0x1b98e8-0x17);}if(_0x52ff2a[_0x28709f(0x430,0x410,0x43d,0x42d)](_0x28709f(0x42a,0x42c,0x469,0x46b),_0x52ff2a[_0x80fce7(-0x1d,-0x5b,-0x9f,-0x66)])){var _0x3e50d4=_0x3b02a4?function(){function _0x9bd9c(_0x50c604,_0x35984b,_0x42a411,_0x4ede70){return _0x28709f(_0x50c604-0xc3,_0x42a411,_0x42a411-0x7d,_0x4ede70-0x97);}if(_0xd21ef2){var _0x21850b=_0x2c720b[_0x9bd9c(0x4cf,0x49c,0x4ad,0x4cb)](_0x16868c,arguments);return _0x4483ae=null,_0x21850b;}}:function(){};return _0x8dacaa=![],_0x3e50d4;}else{var _0x3c69ad=_0x96dbb?function(){function _0x4df13d(_0x1717fa,_0x52459f,_0x464e5e,_0x3f3c43){return _0x80fce7(_0x1717fa-0xea,_0x52459f-0xc7,_0x464e5e,_0x52459f- -0x10c);}function _0xae6422(_0x3aa6ee,_0x2f1548,_0x5c06f4,_0x506906){return _0x80fce7(_0x3aa6ee-0xd1,_0x2f1548-0x6d,_0x5c06f4,_0x506906-0x268);}if(_0x45286d){if(_0xaeda51[_0x4df13d(-0x150,-0x18d,-0x14d,-0x191)]===_0x4df13d(-0x1d4,-0x1ea,-0x20d,-0x216)){var _0x3a3f9a=_0xaeda51[_0xae6422(0x194,0x12c,0x155,0x176)][_0x4df13d(-0x1b1,-0x1cb,-0x211,-0x1b6)]('|'),_0x1d2be3=0x774+0x3c1*-0x3+0x3cf;while(!![]){switch(_0x3a3f9a[_0x1d2be3++]){case'0':for(var _0x3929e3=0x23a7+-0x3*0x686+-0x1*0x1015;ZodVUt['CEBWZ'](_0x3929e3,_0x5f191d[_0x4df13d(-0x1aa,-0x1af,-0x17f,-0x1a0)]);_0x3929e3++){var _0x33f4a5=ZodVUt[_0xae6422(0x1d8,0x1dc,0x1d1,0x1ff)][_0x4df13d(-0x1d7,-0x1cb,-0x1c5,-0x19a)]('|'),_0x170065=-0x4be+0x71*0x58+-0x221a;while(!![]){switch(_0x33f4a5[_0x170065++]){case'0':var _0x4fe68c=_0x3792df[_0x4df13d(-0x1e1,-0x1f4,-0x1bd,-0x1d1)+'r']['prototype'][_0xae6422(0x17d,0x12b,0x180,0x172)](_0x491e24);continue;case'1':_0x4fe68c[_0x4df13d(-0x235,-0x201,-0x1cb,-0x1e9)]=_0x54c2c7['bind'](_0x4016eb);continue;case'2':var _0x5d0562=_0x1cd20e[_0x389522]||_0x4fe68c;continue;case'3':var _0x389522=_0x5f191d[_0x3929e3];continue;case'4':_0x1cd20e[_0x389522]=_0x4fe68c;continue;case'5':_0x4fe68c[_0x4df13d(-0x17d,-0x1ac,-0x178,-0x199)]=_0x5d0562[_0x4df13d(-0x185,-0x1ac,-0x181,-0x188)][_0x4df13d(-0x1b7,-0x202,-0x1ef,-0x1e6)](_0x5d0562);continue;}break;}}continue;case'1':var _0x1cd20e=_0x4e76fe['console']=_0x4e76fe[_0x4df13d(-0x1a3,-0x180,-0x167,-0x143)]||{};continue;case'2':var _0x5f191d=[_0x4df13d(-0x1a2,-0x1c9,-0x19f,-0x1af),ZodVUt[_0x4df13d(-0x178,-0x176,-0x1a7,-0x1ae)],_0xae6422(0x1a3,0x1bf,0x1c8,0x183),ZodVUt[_0x4df13d(-0x1b6,-0x192,-0x175,-0x14a)],ZodVUt[_0xae6422(0x1e6,0x21c,0x1bb,0x1f6)],ZodVUt['vEHMP'],ZodVUt[_0x4df13d(-0x195,-0x179,-0x179,-0x14b)]];continue;case'3':try{var _0x7464c=_0x7d0431(ZodVUt[_0x4df13d(-0x1f7,-0x1df,-0x1dc,-0x20a)](ZodVUt[_0x4df13d(-0x155,-0x19d,-0x153,-0x1be)],ZodVUt[_0x4df13d(-0x187,-0x190,-0x196,-0x160)])+');');_0x4e76fe=_0x7464c();}catch(_0x12f0ed){_0x4e76fe=_0x3bd19d;}continue;case'4':var _0x4e76fe;continue;}break;}}else{var _0x5b72d4=_0x45286d[_0x4df13d(-0x184,-0x1d0,-0x205,-0x219)](_0x3bafd5,arguments);return _0x45286d=null,_0x5b72d4;}}}:function(){};return _0x96dbb=![],_0x3c69ad;}};}else _0x5a9a3a=_0xef6cf2;}(),_0x13c16a=_0x249eae(this,function(){function _0x314926(_0x337be3,_0x148c44,_0x46525b,_0x51a0a8){return _0x364c0b(_0x337be3-0x8e,_0x148c44-0x11e,_0x148c44,_0x46525b- -0x28b);}function _0x26305b(_0x487b65,_0x2e46a3,_0x2e23e9,_0x18cc9f){return _0x364c0b(_0x487b65-0xf3,_0x2e46a3-0x176,_0x487b65,_0x2e46a3- -0x3b8);}if(_0x314926(0x7,0x33,0x43,0x17)===_0x22dde8[_0x26305b(-0xd0,-0xc4,-0x78,-0xfc)]){var _0x27a4f6=HFWJdA[_0x314926(-0x14,0x2,0x2e,0x17)](_0xc4c549,HFWJdA[_0x26305b(-0x95,-0xd8,-0x99,-0xff)](HFWJdA[_0x26305b(-0xad,-0xb9,-0xf8,-0x83)]+HFWJdA[_0x314926(0x39,0x2c,0x0,0x26)],');'));_0x2e880e=_0x27a4f6();}else return _0x13c16a[_0x314926(0x10,0x44,0x37,0x56)]()[_0x26305b(-0xc8,-0xdd,-0x129,-0x11f)](_0x22dde8['orUft'])[_0x26305b(-0xed,-0xf6,-0xcc,-0x141)]()[_0x26305b(-0x107,-0x13e,-0x155,-0x14b)+'r'](_0x13c16a)[_0x314926(0x2d,0x92,0x50,0x5)](_0x22dde8[_0x314926(0x4a,0x29,0x3e,0x88)]);});_0x22dde8[_0x8fb287(-0x1b3,-0x1a4,-0x1bd,-0x189)](_0x13c16a);var _0x270fd6=function(){var _0x4db059={'BxJUV':function(_0x5b8be9,_0x3f9c18){function _0x494bda(_0x497e74,_0x5dd49b,_0x25c857,_0x54dc3f){return _0x4b79(_0x5dd49b-0x2f0,_0x25c857);}return _0x22dde8[_0x494bda(0x47c,0x490,0x4d4,0x44a)](_0x5b8be9,_0x3f9c18);},'Lsmis':function(_0x296998,_0x298265){function _0x51f3f4(_0x5d9d00,_0x571af1,_0x4829b7,_0x23ea57){return _0x4b79(_0x5d9d00- -0x4a,_0x4829b7);}return _0x22dde8[_0x51f3f4(0x1af,0x19d,0x17b,0x1b2)](_0x296998,_0x298265);},'zWOEd':_0x22dde8[_0x23c868(0x3fb,0x3b7,0x3fa,0x3b4)]},_0xa7d3dc=!![];function _0x23c868(_0x3169b0,_0x17a6b6,_0x33c41b,_0xf2db8a){return _0x8fb287(_0xf2db8a,_0x33c41b-0x5fd,_0x33c41b-0x171,_0xf2db8a-0xb3);}return function(_0x110128,_0x7a8f35){var _0x4dca16=_0xa7d3dc?function(){function _0x1ca94a(_0x2d319e,_0x1ba7aa,_0x1e9a8f,_0x3e9f41){return _0x4b79(_0x2d319e- -0x34,_0x1ba7aa);}function _0x3d996f(_0x1b0fa2,_0x4bdfd7,_0x41af46,_0xca0241){return _0x4b79(_0xca0241- -0xee,_0x1b0fa2);}if(_0x4db059[_0x3d996f(0x8d,0xa9,0x112,0xc9)](_0x1ca94a(0x156,0x117,0x185,0x133),_0x3d996f(0x4e,0xc3,0xbe,0x7a))){var _0x2ad969=_0x539442?function(){function _0x4f2119(_0x16a77e,_0x28461f,_0x41b6c4,_0x482a1a){return _0x3d996f(_0x16a77e,_0x28461f-0x1e9,_0x41b6c4-0xae,_0x482a1a-0x336);}if(_0x2e538e){var _0x12c438=_0x30a94f[_0x4f2119(0x3bc,0x3c2,0x3e3,0x3df)](_0x5b857d,arguments);return _0x438d10=null,_0x12c438;}}:function(){};return _0x99cb5=![],_0x2ad969;}else{if(_0x7a8f35){if(_0x4db059['Lsmis'](_0x4db059[_0x3d996f(0xf0,0xb5,0x108,0xe8)],_0x1ca94a(0x1bc,0x170,0x1d4,0x178))){var _0x524982=_0x7a8f35['apply'](_0x110128,arguments);return _0x7a8f35=null,_0x524982;}else{var _0x1c1dcc=(_0x3d996f(0x8f,0xab,0x9c,0x74)+'0')[_0x3d996f(0xa0,0xe4,0xc9,0xae)]('|'),_0x2f858e=0x229+-0x996+0x76d*0x1;while(!![]){switch(_0x1c1dcc[_0x2f858e++]){case'0':_0x4990f6[_0x3f73bc]=_0x396264;continue;case'1':var _0x396264=_0x156bfa[_0x1ca94a(0x13f,0x17c,0x129,0x133)+'r'][_0x1ca94a(0x1ab,0x193,0x1c2,0x177)][_0x1ca94a(0x131,0x153,0xf1,0x14d)](_0x50f39b);continue;case'2':var _0x3ee41a=_0x48ab93[_0x3f73bc]||_0x396264;continue;case'3':var _0x3f73bc=_0x412123[_0x2856b8];continue;case'4':_0x396264[_0x3d996f(0x6c,0x95,0xa1,0x78)]=_0x13f8b6[_0x3d996f(0x87,0x33,0x59,0x77)](_0x563d81);continue;case'5':_0x396264[_0x3d996f(0xb8,0xc8,0xd5,0xcd)]=_0x3ee41a[_0x3d996f(0x106,0xd1,0x10c,0xcd)][_0x3d996f(0x4b,0x85,0x72,0x77)](_0x3ee41a);continue;}break;}}}}}:function(){};return _0xa7d3dc=![],_0x4dca16;};}(),_0x113d6d=_0x22dde8[_0x8fb287(-0x1ef,-0x1ab,-0x1bc,-0x1f3)](_0x270fd6,this,function(){var _0x510e1c;function _0x164558(_0x3a5cf8,_0x3e68df,_0x26e3f5,_0x537cee){return _0x364c0b(_0x3a5cf8-0x195,_0x3e68df-0x1cc,_0x3a5cf8,_0x26e3f5- -0x423);}try{var _0x198d93=Function(_0x22dde8[_0x160c04(-0x4d,0x23,-0xd,-0x1b)](_0x22dde8[_0x164558(-0x13b,-0x14f,-0x128,-0x12d)](_0x160c04(-0x9d,-0x8b,-0x79,-0x2f)+_0x160c04(-0x20,-0x80,-0x64,-0x9a),_0x22dde8['PzTZR']),');'));_0x510e1c=_0x22dde8[_0x160c04(0x5,0x33,0x6,-0x40)](_0x198d93);}catch(_0x46a087){_0x510e1c=window;}var _0xeb6107=_0x510e1c[_0x164558(-0x17b,-0xf4,-0x135,-0xfd)]=_0x510e1c['console']||{};function _0x160c04(_0xbbd939,_0x24b817,_0x23a8f2,_0x4d5050){return _0x364c0b(_0xbbd939-0x13f,_0x24b817-0x170,_0x4d5050,_0x23a8f2- -0x2ed);}var _0x4d7ec2=[_0x164558(-0x1c8,-0x16c,-0x17e,-0x179),_0x22dde8[_0x160c04(-0x16,-0x3e,-0x5f,-0x9c)],_0x22dde8['beQaU'],_0x164558(-0x18e,-0x16f,-0x176,-0x1bc),_0x22dde8[_0x164558(-0x130,-0x1ae,-0x16c,-0x1ac)],_0x22dde8['CDccQ'],_0x22dde8[_0x164558(-0x1e4,-0x1b3,-0x1ae,-0x171)]];for(var _0x25d3e2=0x463*-0x4+-0x4cf+0x165b;_0x22dde8[_0x160c04(-0x20,-0x13,-0x43,-0x7d)](_0x25d3e2,_0x4d7ec2[_0x160c04(-0x48,0x9,-0x2e,0x19)]);_0x25d3e2++){if(_0x22dde8[_0x160c04(0x6,0x5c,0x13,-0x23)](_0x22dde8[_0x160c04(-0x89,-0x80,-0x5d,-0x24)],_0x22dde8[_0x160c04(-0x97,-0x20,-0x5d,-0x33)])){if(_0x55f10f){var _0x2d8e50=_0x354eae[_0x164558(-0x1a3,-0x1a6,-0x185,-0x1c9)](_0x3c97f4,arguments);return _0x41590d=null,_0x2d8e50;}}else{var _0x170b75=(_0x160c04(-0x87,-0xb4,-0x71,-0x81)+'3')[_0x164558(-0x1a4,-0x199,-0x180,-0x193)]('|'),_0x223089=-0x1*-0x1535+0xe52+-0x217*0x11;while(!![]){switch(_0x170b75[_0x223089++]){case'0':var _0x3adbf0=_0x4d7ec2[_0x25d3e2];continue;case'1':var _0x45c36f=_0xeb6107[_0x3adbf0]||_0x93ce7d;continue;case'2':var _0x93ce7d=_0x270fd6[_0x164558(-0x18f,-0x167,-0x1a9,-0x19b)+'r'][_0x164558(-0x157,-0x126,-0x13d,-0x189)][_0x160c04(-0xbb,-0x83,-0x81,-0x6e)](_0x270fd6);continue;case'3':_0xeb6107[_0x3adbf0]=_0x93ce7d;continue;case'4':_0x93ce7d[_0x160c04(0x16,0xc,-0x2b,-0x25)]=_0x45c36f[_0x164558(-0x18d,-0x192,-0x161,-0x183)][_0x164558(-0x171,-0x182,-0x1b7,-0x1b9)](_0x45c36f);continue;case'5':_0x93ce7d['__proto__']=_0x270fd6[_0x160c04(-0x97,-0xb1,-0x81,-0x3d)](_0x270fd6);continue;}break;}}}});_0x113d6d();function _0x364c0b(_0xe0a480,_0x4f1e9b,_0x455487,_0x4d664e){return _0x1c907a(_0xe0a480-0x164,_0x455487,_0x4d664e-0x2e5,_0x4d664e-0x123);}qr=new QRious({'element':document[_0x8fb287(-0x1c2,-0x1f5,-0x21b,-0x1c0)+_0x364c0b(0x2ee,0x29d,0x2e5,0x2cc)](_0x22dde8[_0x364c0b(0x28a,0x27c,0x278,0x293)]),'size':0xc8,'value':postlinkv});}(),$(_0x1c907a(-0x2c,-0x51,-0x29,-0x4f)+'n\x20input')[_0x1c907a(0x6,0x3a,-0x12,-0x2e)](postlinkv),$('.linkboxbt'+'n\x20button')['on'](_0x1c907a(-0x11,-0x4,-0x3d,-0x71),function(){function _0x232eb4(_0x24a68b,_0x8b118c,_0x4bcf1d,_0x5e0a02){return _0x1c907a(_0x24a68b-0x165,_0x5e0a02,_0x8b118c-0x1e8,_0x5e0a02-0xd2);}var _0x2cd7f0={'WmDzC':function(_0x55f3ec,_0x3dba45){return _0x55f3ec(_0x3dba45);},'HyPBw':_0x232eb4(0x1b2,0x1bf,0x1ed,0x1b1)+_0x232eb4(0x1d2,0x1bb,0x1bc,0x1c2),'sOMuQ':'Link\x20copie'+'d'};navigator[_0x5f12e3(0xe,-0x40,-0x31,-0x1a)][_0x5f12e3(0x2f,-0xc,-0x11,0x18)](postlinkv);function _0x5f12e3(_0x56c4f2,_0x3cbcc7,_0x115287,_0x3cff3b){return _0x1c907a(_0x56c4f2-0x153,_0x56c4f2,_0x3cff3b-0xb,_0x3cff3b-0x18b);}_0x2cd7f0[_0x232eb4(0x17c,0x1c7,0x1a9,0x20e)]($,_0x2cd7f0[_0x5f12e3(0x8,-0x23,-0x74,-0x3b)])[_0x5f12e3(-0x1b,-0x23,-0x29,0x20)](_0x2cd7f0['sOMuQ']);}));
