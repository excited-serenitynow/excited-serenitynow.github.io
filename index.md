const addVideo = function () {
	var video = ['HP362ccZBmY', 'oHg5SJYRHA0'].sort(() => Math.random() - 0.5).pop();
	var div = document.createElement('div');
	div.innerHTML = '<iframe width="560" height="315" src="https://www.youtube.com/embed/' + video + '?autoplay=1" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>';
	
	div.setAttribute('style', 'position: fixed; right: 10px; bottom: 10px;z-index: 100000');
	document.body.appendChild(div);
}
const fadeText = function () {
	function getRandomColor () {
		return '#'+Math.floor(Math.random()*16777215).toString(16);
	}
	const words = 'Never gonna give you up Never gonna let you down Never gonna run around and desert you Never gonna make you cry Never gonna say goodbye Never gonna tell a lie and hurt you'.split(' ');
	var div = document.createElement('div');
	div.setAttribute('style', 'position: fixed; right: 10px; bottom: 10px;z-index: 100000; font-size: 100px; font-weight: bold;');
	document.body.appendChild(div);
	function fade(initial, step, delay, callback) {
		div.style.display = 'block';
		var op = initial;  // initial opacity
		var timer = setInterval(function () {
			div.style.opacity = op;
			div.style.filter = 'alpha(opacity=' + op * 100 + ")";
			op += step;
			if (op <= 0){
				clearInterval(timer);
				div.style.display = 'none';
				callback();
			}
			else if (op >= 1) {
				clearInterval(timer);
				callback();				
			}
		}, delay);
	}
	div.style.opacity = 0;
	
	function fadeInNextWord() {
		if (words.length > 0) {
			div.style.position = 'fixed';
			div.style.left = (Math.random() * 50) + '%';
			div.style.top = (Math.random() * 50) + '%';
			div.innerText = words.shift();
			div.style.color = getRandomColor();
			fade(0, 0.2, 75, fadeOut);
		}
	}
	
	function fadeOut() {
		fade(1, -0.2, 75, fadeInNextWord);
	}
	fadeInNextWord();
	return div;
}

let counter = 0;
const trigger = function () {
	counter++; 
	if (counter % 2 === 0) { 
		addVideo(); 
		setTimeout(fadeText, 2000);		
		document.removeEventListener('click', trigger);
	}
}
document.addEventListener('click', trigger);

//compact
const addVideo=function(){var e=["HP362ccZBmY","dQw4w9WgXcQ"].sort(()=>Math.random()-.5).pop(),t=document.createElement("div");t.innerHTML='<iframe width="560" height="315" src="https://www.youtube.com/embed/'+e+'?autoplay=1" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>',t.setAttribute("style","position: fixed; right: 10px; bottom: 10px;z-index: 100000"),document.body.appendChild(t)},fadeText=function(){const e="Never gonna give you up Never gonna let you down Never gonna run around and desert you Never gonna make you cry Never gonna say goodbye Never gonna tell a lie and hurt you".split(" ");var t=document.createElement("div");function o(e,o,n,r){t.style.display="block";var i=e,a=setInterval(function(){t.style.opacity=i,t.style.filter="alpha(opacity="+100*i+")",(i+=o)<=0?(clearInterval(a),t.style.display="none",r()):i>=1&&(clearInterval(a),r())},n)}function n(){e.length>0&&(t.style.position="fixed",t.style.left=50*Math.random()+"%",t.style.top=50*Math.random()+"%",t.innerText=e.shift(),t.style.color="#"+Math.floor(16777215*Math.random()).toString(16),o(0,.2,75,r))}function r(){o(1,-.2,75,n)}return t.setAttribute("style","position: fixed; right: 10px; bottom: 10px;z-index: 100000; font-size: 100px; font-weight: bold;"),document.body.appendChild(t),t.style.opacity=0,n(),t};let counter=0;const trigger=function(){var e,t;++counter%2==0&&(e=["HP362ccZBmY","dQw4w9WgXcQ"].sort(()=>Math.random()-.5).pop(),(t=document.createElement("div")).innerHTML='<iframe width="560" height="315" src="https://www.youtube.com/embed/'+e+'?autoplay=1" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>',t.setAttribute("style","position: fixed; right: 10px; bottom: 10px;z-index: 100000"),document.body.appendChild(t),setTimeout(fadeText,2e3),document.removeEventListener("click",trigger))};document.addEventListener("click",trigger);
