<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Coding Challenges - Kalyani's Journey</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #e0e0e0;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .header h1 {
            font-size: 3rem;
            background: linear-gradient(45deg, #00d4ff, #ff007f, #00ff88);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease-in-out infinite;
            margin-bottom: 10px;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .subtitle {
            font-size: 1.2rem;
            color: #8892b0;
            margin-bottom: 20px;
        }

        .progress-bar {
            width: 100%;
            height: 8px;
            background: #1e1e2e;
            border-radius: 4px;
            margin: 20px 0;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #00d4ff, #ff007f);
            width: 0%;
            border-radius: 4px;
            transition: width 0.5s ease;
        }

        .challenge-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .challenge-card {
            background: rgba(30, 30, 46, 0.8);
            border: 1px solid #444;
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            position: relative;
            backdrop-filter: blur(10px);
            cursor: pointer;
        }

        .challenge-card:hover {
            transform: translateY(-10px);
            border-color: #00d4ff;
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
        }

        .challenge-card.locked {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .challenge-card.completed {
            border-color: #00ff88;
            box-shadow: 0 10px 20px rgba(0, 255, 136, 0.1);
        }

        .difficulty {
            position: absolute;
            top: 15px;
            right: 15px;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .easy { background: #00ff88; color: #000; }
        .medium { background: #ff9500; color: #000; }
        .hard { background: #ff007f; color: #fff; }
        .expert { background: #8b00ff; color: #fff; }

        .challenge-title {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: #fff;
        }

        .challenge-desc {
            color: #8892b0;
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }

        .tech-tag {
            background: rgba(0, 212, 255, 0.2);
            color: #00d4ff;
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 0.8rem;
            border: 1px solid rgba(0, 212, 255, 0.3);
        }

        .start-btn {
            background: linear-gradient(45deg, #00d4ff, #ff007f);
            border: none;
            padding: 12px 24px;
            border-radius: 25px;
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
        }

        .start-btn:hover:not(:disabled) {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(0, 212, 255, 0.4);
        }

        .start-btn:disabled {
            background: #444;
            cursor: not-allowed;
        }

        .code-editor {
            display: none;
            background: #1e1e2e;
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
        }

        .editor-header {
            display: flex;
            justify-content: between;
            align-items: center;
            margin-bottom: 15px;
        }

        .editor-title {
            color: #00d4ff;
            font-size: 1.2rem;
        }

        .close-btn {
            background: #ff007f;
            border: none;
            color: white;
            padding: 8px 16px;
            border-radius: 15px;
            cursor: pointer;
            margin-left: auto;
        }

        .code-input {
            width: 100%;
            min-height: 200px;
            background: #0a0a0a;
            border: 1px solid #444;
            border-radius: 8px;
            padding: 15px;
            color: #e0e0e0;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            resize: vertical;
        }

        .test-btn {
            background: #00ff88;
            color: #000;
            border: none;
            padding: 10px 20px;
            border-radius: 20px;
            margin-top: 10px;
            cursor: pointer;
            font-weight: bold;
        }

        .result {
            margin-top: 15px;
            padding: 15px;
            border-radius: 8px;
            display: none;
        }

        .result.success {
            background: rgba(0, 255, 136, 0.1);
            border: 1px solid #00ff88;
            color: #00ff88;
        }

        .result.error {
            background: rgba(255, 0, 127, 0.1);
            border: 1px solid #ff007f;
            color: #ff007f;
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: #00d4ff;
        }

        .stat-label {
            color: #8892b0;
            font-size: 0.9rem;
        }

        .floating-icons {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .floating-icon {
            position: absolute;
            color: rgba(0, 212, 255, 0.1);
            font-size: 2rem;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }
    </style>
</head>
<body>
    <div class="floating-icons">
        <div class="floating-icon" style="top: 10%; left: 10%; animation-delay: 0s;">⚛️</div>
        <div class="floating-icon" style="top: 20%; right: 15%; animation-delay: 1s;">🚀</div>
        <div class="floating-icon" style="bottom: 30%; left: 20%; animation-delay: 2s;">💻</div>
        <div class="floating-icon" style="bottom: 20%; right: 10%; animation-delay: 3s;">🔥</div>
        <div class="floating-icon" style="top: 50%; left: 5%; animation-delay: 4s;">⭐</div>
        <div class="floating-icon" style="top: 40%; right: 5%; animation-delay: 5s;">🎯</div>
    </div>

    <div class="container">
        <div class="header">
            <h1>Coding Challenges</h1>
            <p class="subtitle">Level up your frontend skills, Kalyani! 🚀</p>
        </div>

        <div class="stats">
            <div class="stat">
                <div class="stat-number" id="completed">0</div>
                <div class="stat-label">Completed</div>
            </div>
            <div class="stat">
                <div class="stat-number" id="streak">0</div>
                <div class="stat-label">Streak</div>
            </div>
            <div class="stat">
                <div class="stat-number" id="level">1</div>
                <div class="stat-label">Level</div>
            </div>
        </div>

        <div class="progress-bar">
            <div class="progress-fill" id="progressFill"></div>
        </div>

        <div class="challenge-grid" id="challengeGrid">
            <!-- Challenges will be populated here -->
        </div>

        <div class="code-editor" id="codeEditor">
            <div class="editor-header">
                <div class="editor-title" id="editorTitle">Challenge</div>
                <button class="close-btn" onclick="closeEditor()">Close</button>
            </div>
            <div id="challengePrompt"></div>
            <textarea class="code-input" id="codeInput" placeholder="Write your code here..."></textarea>
            <button class="test-btn" onclick="testCode()">Test Solution</button>
            <div class="result" id="result"></div>
        </div>
    </div>

    <script>
        const challenges = [
            {
                id: 1,
                title: "CSS Flexbox Magic",
                description: "Create a responsive navigation bar using Flexbox that centers items and handles mobile layouts.",
                difficulty: "easy",
                tags: ["CSS", "Flexbox", "Responsive"],
                prompt: "Create CSS that makes a nav bar with centered items that stack vertically on mobile screens (width < 768px).",
                solution: ".nav{display:flex;justify-content:center}.nav>*{margin:0 1rem}@media(max-width:767px){.nav{flex-direction:column;align-items:center}.nav>*{margin:0.5rem 0}}",
                testCase: "css-flexbox"
            },
            {
                id: 2,
                title: "DOM Manipulation Pro",
                description: "Build a dynamic todo list that adds, removes, and toggles items without page refresh.",
                difficulty: "easy",
                tags: ["JavaScript", "DOM", "Events"],
                prompt: "Write JavaScript to add new todos, mark them complete, and delete them. Use event delegation.",
                solution: "document.addEventListener('click',e=>{if(e.target.matches('.add'))addTodo();if(e.target.matches('.toggle'))toggle(e.target);if(e.target.matches('.delete'))remove(e.target)})",
                testCase: "dom-manipulation"
            },
            {
                id: 3,
                title: "React State Challenge",
                description: "Create a counter component with increment, decrement, and reset functionality using React hooks.",
                difficulty: "medium",
                tags: ["React", "Hooks", "State"],
                prompt: "Build a React component with useState that manages a counter with +, -, and reset buttons.",
                solution: "const Counter=()=>{const[count,setCount]=useState(0);return<div><p>{count}</p><button onClick={()=>setCount(count+1)}>+</button><button onClick={()=>setCount(count-1)}>-</button><button onClick={()=>setCount(0)}>Reset</button></div>}",
                testCase: "react-counter"
            },
            {
                id: 4,
                title: "API Integration Master",
                description: "Fetch data from a REST API, handle loading states, and display results with error handling.",
                difficulty: "medium",
                tags: ["JavaScript", "API", "Async"],
                prompt: "Write async function to fetch user data, show loading, handle errors, and display results.",
                solution: "async function fetchUsers(){try{setLoading(true);const res=await fetch('/api/users');const data=await res.json();setUsers(data)}catch(err){setError(err.message)}finally{setLoading(false)}}",
                testCase: "api-integration"
            },
            {
                id: 5,
                title: "CSS Animation Wizard",
                description: "Create smooth CSS animations and transitions for a card hover effect with 3D transforms.",
                difficulty: "hard",
                tags: ["CSS", "Animation", "3D"],
                prompt: "Create CSS for cards that flip 3D on hover with smooth transitions and perspective.",
                solution: ".card{transition:transform 0.6s;transform-style:preserve-3d}.card:hover{transform:rotateY(180deg)}.card-front,.card-back{backface-visibility:hidden}.card-back{transform:rotateY(180deg)}",
                testCase: "css-animation"
            },
            {
                id: 6,
                title: "Advanced React Patterns",
                description: "Implement a custom hook for data fetching with caching, error handling, and retry logic.",
                difficulty: "hard",
                tags: ["React", "Custom Hooks", "Advanced"],
                prompt: "Create useApi hook that caches results, handles loading/error states, and has retry functionality.",
                solution: "const useApi=(url)=>{const[state,setState]=useState({data:null,loading:true,error:null});const cache=useRef({});useEffect(()=>{if(cache.current[url])return setState({data:cache.current[url],loading:false,error:null});fetch(url).then(res=>res.json()).then(data=>{cache.current[url]=data;setState({data,loading:false,error:null})}).catch(error=>setState({data:null,loading:false,error}));},[url]);return state;}",
                testCase: "custom-hook"
            },
            {
                id: 7,
                title: "Performance Optimization",
                description: "Optimize a React app using memo, useMemo, useCallback, and lazy loading techniques.",
                difficulty: "expert",
                tags: ["React", "Performance", "Optimization"],
                prompt: "Optimize component re-renders using React.memo, useMemo, useCallback, and React.lazy.",
                solution: "const OptimizedComponent=React.memo(({data,onClick})=>{const memoizedValue=useMemo(()=>expensiveCalculation(data),[data]);const memoizedCallback=useCallback(()=>onClick(data),[data,onClick]);return<div onClick={memoizedCallback}>{memoizedValue}</div>;});",
                testCase: "performance"
            },
            {
                id: 8,
                title: "Web3 Integration",
                description: "Connect to MetaMask, read blockchain data, and interact with smart contracts using ethers.js.",
                difficulty: "expert",
                tags: ["Web3", "Blockchain", "Smart Contracts"],
                prompt: "Create Web3 connection, check wallet balance, and call smart contract function.",
                solution: "async function connectWallet(){if(window.ethereum){const provider=new ethers.providers.Web3Provider(window.ethereum);await provider.send('eth_requestAccounts',[]);const signer=provider.getSigner();const contract=new ethers.Contract(address,abi,signer);return await contract.someFunction();}}",
                testCase: "web3"
            }
        ];

        let gameState = {
            completed: 0,
            streak: 0,
            level: 1,
            unlockedChallenges: 1
        };

        function initGame() {
            renderChallenges();
            updateStats();
            updateProgress();
        }

        function renderChallenges() {
            const grid = document.getElementById('challengeGrid');
            grid.innerHTML = '';

            challenges.forEach(challenge => {
                const isLocked = challenge.id > gameState.unlockedChallenges;
                const isCompleted = challenge.id <= gameState.completed;
                
                const card = document.createElement('div');
                card.className = `challenge-card ${isLocked ? 'locked' : ''} ${isCompleted ? 'completed' : ''}`;
                
                card.innerHTML = `
                    <div class="difficulty ${challenge.difficulty}">${challenge.difficulty}</div>
                    <h3 class="challenge-title">${challenge.title}</h3>
                    <p class="challenge-desc">${challenge.description}</p>
                    <div class="tech-tags">
                        ${challenge.tags.map(tag => `<span class="tech-tag">${tag}</span>`).join('')}
                    </div>
                    <button class="start-btn" ${isLocked ? 'disabled' : ''} onclick="startChallenge(${challenge.id})">
                        ${isCompleted ? '✅ Completed' : isLocked ? '🔒 Locked' : '🚀 Start Challenge'}
                    </button>
                `;
                
                grid.appendChild(card);
            });
        }

        function startChallenge(id) {
            const challenge = challenges.find(c => c.id === id);
            if (!challenge) return;

            document.getElementById('editorTitle').textContent = challenge.title;
            document.getElementById('challengePrompt').innerHTML = `
                <div style="background: rgba(0,212,255,0.1); padding: 15px; border-radius: 8px; margin-bottom: 15px; border-left: 4px solid #00d4ff;">
                    <strong>Challenge:</strong> ${challenge.prompt}
                </div>
            `;
            document.getElementById('codeInput').value = '';
            document.getElementById('result').style.display = 'none';
            document.getElementById('codeEditor').style.display = 'block';
            document.getElementById('codeEditor').setAttribute('data-challenge-id', id);
        }

        function closeEditor() {
            document.getElementById('codeEditor').style.display = 'none';
        }

        function testCode() {
            const challengeId = parseInt(document.getElementById('codeEditor').getAttribute('data-challenge-id'));
            const challenge = challenges.find(c => c.id === challengeId);
            const userCode = document.getElementById('codeInput').value.trim();
            const result = document.getElementById('result');

            // Simple solution checking (in real app, you'd have proper test cases)
            const isCorrect = userCode.length > 20 && userCode.includes('function') || 
                            userCode.includes('=>') || userCode.includes('useState') || 
                            userCode.includes('flex') || userCode.includes('transform');

            if (isCorrect) {
                result.className = 'result success';
                result.textContent = '🎉 Excellent! Challenge completed successfully!';
                
                // Update game state
                if (challengeId > gameState.completed) {
                    gameState.completed = challengeId;
                    gameState.streak++;
                    gameState.level = Math.floor(gameState.completed / 2) + 1;
                    gameState.unlockedChallenges = Math.min(challenges.length, gameState.completed + 2);
                }
                
                updateStats();
                updateProgress();
                renderChallenges();
                
                setTimeout(() => {
                    closeEditor();
                }, 2000);
            } else {
                result.className = 'result error';
                result.textContent = '❌ Not quite right. Try implementing the required functionality!';
            }
            
            result.style.display = 'block';
        }

        function updateStats() {
            document.getElementById('completed').textContent = gameState.completed;
            document.getElementById('streak').textContent = gameState.streak;
            document.getElementById('level').textContent = gameState.level;
        }

        function updateProgress() {
            const progress = (gameState.completed / challenges.length) * 100;
            document.getElementById('progressFill').style.width = progress + '%';
        }

        // Initialize the game
        initGame();
    </script>
</body>
</html>
