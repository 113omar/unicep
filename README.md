<title>Fundación MOVAPE/UNICEP - Acceso al Portal</title> 
<style> 
    body { 
        box-sizing: border-box; 
        margin: 0; 
        padding: 0; 
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
        overflow-x: hidden; 
        background: linear-gradient(135deg, #87CEEB 0%, #6B8E23 100%); 
        min-height: 100vh; 
    }
    .animated-bg {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: -1;
        overflow: hidden;
    }

    .sphere {
        position: absolute;
        border-radius: 50%;
        background: linear-gradient(45deg, rgba(255,255,255,0.1), rgba(255,255,255,0.3));
        backdrop-filter: blur(10px);
        animation: float 6s ease-in-out infinite;
    }

    .sphere:nth-child(1) {
        width: 80px;
        height: 80px;
        top: 20%;
        left: 10%;
        animation-delay: 0s;
    }

    .sphere:nth-child(2) {
        width: 120px;
        height: 120px;
        top: 60%;
        right: 15%;
        animation-delay: 2s;
    }

    .sphere:nth-child(3) {
        width: 60px;
        height: 60px;
        top: 80%;
        left: 20%;
        animation-delay: 4s;
    }

    .sphere:nth-child(4) {
        width: 100px;
        height: 100px;
        top: 30%;
        right: 30%;
        animation-delay: 1s;
    }

    .sphere:nth-child(5) {
        width: 90px;
        height: 90px;
        top: 10%;
        left: 60%;
        animation-delay: 3s;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0px) rotate(0deg); }
        50% { transform: translateY(-20px) rotate(180deg); }
    }

    .container {
        position: relative;
        z-index: 1;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
    }

    .login-section {
        flex: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 2rem;
        text-align: center;
    }

    .dashboard-section {
        display: none;
        flex-direction: column;
        flex: 1;
        padding: 2rem;
        max-width: 1200px;
        margin: 0 auto;
        width: 100%;
    }

    .logo {
        background: rgba(255,255,255,0.9);
        padding: 2rem;
        border-radius: 20px;
        margin-bottom: 2rem;
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        backdrop-filter: blur(10px);
    }

    .logo h1 {
        margin: 0;
        color: #2c5530;
        font-size: 2.5rem;
        font-weight: bold;
    }

    .logo p {
        margin: 0.5rem 0 0 0;
        color: #4682B4;
        font-size: 1.2rem;
    }

    .login-form {
        background: rgba(255,255,255,0.9);
        padding: 3rem;
        border-radius: 20px;
        box-shadow: 0 15px 40px rgba(0,0,0,0.2);
        backdrop-filter: blur(10px);
        max-width: 400px;
        width: 100%;
        margin-top: 2rem;
    }

    .login-form h2 {
        margin: 0 0 2rem 0;
        color: #2c5530;
        font-size: 1.8rem;
    }

    .form-group {
        margin-bottom: 1.5rem;
        text-align: left;
    }

    .form-group label {
        display: block;
        margin-bottom: 0.5rem;
        color: #2c5530;
        font-weight: bold;
    }

    .form-group input, .form-group select, .form-group textarea {
        width: 100%;
        padding: 1rem;
        border: 2px solid #e0e0e0;
        border-radius: 10px;
        font-size: 1rem;
        transition: all 0.3s ease;
        box-sizing: border-box;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
        outline: none;
        border-color: #4682B4;
        box-shadow: 0 0 10px rgba(70, 130, 180, 0.3);
    }

    .login-btn, .action-btn {
        width: 100%;
        background: linear-gradient(45deg, #87CEEB, #6B8E23);
        color: white;
        border: none;
        padding: 1rem;
        border-radius: 10px;
        font-size: 1.1rem;
        font-weight: bold;
        cursor: pointer;
        transition: all 0.3s ease;
        margin-top: 1rem;
    }

    .login-btn:hover, .action-btn:hover {
        transform: translateY(-2px);
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }

    .action-btn {
        width: auto;
        padding: 0.8rem 1.5rem;
        font-size: 1rem;
        margin-top: 0; /* Ajuste para botones dentro de contenedores */
    }

    .action-btn.secondary {
        background: #f0f0f0;
        color: #2c5530;
        border: 1px solid #ddd;
    }

    .action-btn.secondary:hover {
        background: #e0e0e0;
        transform: none;
    }

    .demo-ids {
        background: rgba(255,255,255,0.8);
        padding: 1.5rem;
        border-radius: 15px;
        margin-top: 2rem;
        max-width: 400px;
        width: 100%;
    }

    .demo-ids h3 {
        margin: 0 0 1rem 0;
        color: #2c5530;
        font-size: 1.2rem;
    }

    .demo-id {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0.5rem 0;
        border-bottom: 1px solid #eee;
        font-size: 0.9rem;
    }

    .demo-id:last-child {
        border-bottom: none;
    }

    .demo-id .id-code {
        font-weight: bold;
        color: #4682B4;
        cursor: pointer;
    }

    .demo-id .id-code:hover {
        text-decoration: underline;
    }

    .error-message {
        background: rgba(255, 0, 0, 0.1);
        color: #d32f2f;
        padding: 1rem;
        border-radius: 10px;
        margin-top: 1rem;
        border: 1px solid rgba(255, 0, 0, 0.3);
        display: none;
    }

    .dashboard-header {
        background: rgba(255,255,255,0.9);
        padding: 1.5rem;
        border-radius: 15px;
        margin-bottom: 2rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
        backdrop-filter: blur(10px);
        flex-wrap: wrap;
    }

    .header-controls {
        display: flex;
        gap: 1rem;
        align-items: center;
    }

    .dashboard-header h2 {
        margin: 0;
        color: #2c5530;
    }

    .back-btn {
        background: linear-gradient(45deg, #87CEEB, #6B8E23);
        color: white;
        border: none;
        padding: 0.8rem 1.5rem;
        border-radius: 10px;
        cursor: pointer;
        font-weight: bold;
        transition: all 0.3s ease;
    }

    .back-btn:hover {
        transform: scale(1.05);
        box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }

    .dashboard-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 2rem;
    }

    .dashboard-card {
        background: rgba(255,255,255,0.9);
        padding: 2rem;
        border-radius: 15px;
        box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        backdrop-filter: blur(10px);
        transition: all 0.3s ease;
        display: flex;
        flex-direction: column;
    }

    .dashboard-card:hover {
        transform: translateY(-3px);
        box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        cursor: pointer;
    }

    .dashboard-card.non-clickable:hover {
        transform: none;
        box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        cursor: default;
    }

    .dashboard-card h3 {
        margin: 0 0 1rem 0;
        color: #2c5530;
        display: flex;
        align-items: center;
        gap: 0.5rem;
    }

    .card-content {
        color: #666;
        line-height: 1.6;
        flex-grow: 1;
    }

    .grade-item, .schedule-item-summary, .subject-item, .material-item, .assignment-item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0.75rem 0;
        border-bottom: 1px solid #eee;
    }
    .grade-item:last-child, .schedule-item-summary:last-child, .subject-item:last-child, .material-item:last-child, .assignment-item:last-child {
        border-bottom: none;
    }

    .grade {
        font-weight: bold;
        color: #4682B4;
    }

    .schedule-item {
        background: linear-gradient(45deg, rgba(135,206,235,0.1), rgba(107,142,35,0.1));
        padding: 1rem;
        border-radius: 8px;
        margin-bottom: 0.5rem;
    }

    .calendar-item {
        border-left: 4px solid #6B8E23;
        padding-left: 1rem;
        margin-bottom: 1rem;
    }
    .calendar-item.holiday { border-color: #d32f2f; }
    .calendar-item.event { border-color: #4682B4; }
    .calendar-item.exam { border-color: #FFA500; } 
    .calendar-item strong { color: #2c5530; }


    .schedule-time {
        font-weight: bold;
        color: #2c5530;
    }

    .announcement {
        background: rgba(135,206,235,0.1);
        padding: 1rem;
        border-radius: 8px;
        margin-bottom: 1rem;
        border-left: 4px solid #4682B4;
    }

    .announcement:last-child {
        margin-bottom: 0;
    }

    .announcement-date {
        font-size: 0.9rem;
        color: #666;
        margin-bottom: 0.5rem;
    }

    table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 1rem;
    }
    th, td {
        padding: 0.8rem;
        text-align: left;
        border-bottom: 1px solid #ddd;
    }
    th {
        background-color: rgba(107,142,35,0.1);
        color: #2c5530;
    }

    tr.clickable-row:hover {
        background-color: rgba(107,142,35,0.05);
        cursor: pointer;
    }

    .status-entregado { color: green; font-weight: bold; }
    .status-pendiente { color: orange; font-weight: bold; }
    .attendance-toggle { cursor: pointer; }
    .attendance-Presente { color: green; }
    .attendance-Ausente { color: red; }
    .attendance-Pendiente { color: grey; }

    /* --- ESTILOS PARA CALENDARIO ESTILO GOOGLE --- */
    .calendar-container {
        background: #fff;
        border-radius: 15px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        padding: 2rem;
        margin-bottom: 2rem;
    }

    .calendar-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 1.5rem;
        color: #2c5530;
    }

    .calendar-header h3 {
        font-size: 1.8rem;
        margin: 0;
        color: #2c5530;
    }

    .calendar-nav button {
        background: none;
        border: 1px solid #ddd;
        border-radius: 5px;
        padding: 0.5rem 1rem;
        cursor: pointer;
        font-size: 1rem;
        color: #2c5530;
        transition: background 0.2s;
    }

    .calendar-nav button:hover {
        background: #f0f0f0;
    }

    .calendar-grid {
        display: grid;
        grid-template-columns: repeat(7, 1fr);
        border: 1px solid #e0e0e0;
        border-radius: 8px;
    }

    .calendar-day-name {
        background-color: #f5f5f5;
        color: #666;
        padding: 0.75rem 0.5rem;
        text-align: center;
        font-weight: bold;
        border-bottom: 1px solid #e0e0e0;
    }

    .calendar-day {
        min-height: 100px;
        border-right: 1px solid #e0e0e0;
        border-bottom: 1px solid #e0e0e0;
        padding: 5px;
        overflow: hidden;
        position: relative;
        background-color: #fff;
    }
    .calendar-grid > div:nth-child(7n) { border-right: none; }
    .calendar-grid > div:nth-last-child(-n+7) { border-bottom: none; }

    .day-number {
        font-weight: bold;
        font-size: 1.2rem;
        color: #4682B4;
        display: block;
        margin-bottom: 0.5rem;
        text-align: right;
        padding: 0 5px;
    }

    .day-number.today {
        color: white;
        background: #d32f2f;
        border-radius: 50%;
        display: inline-block;
        padding: 2px 6px;
    }

    .calendar-day.out-month {
        background-color: #fafafa;
        color: #ccc;
    }
    .calendar-day.out-month .day-number {
        color: #ccc;
    }

    .calendar-event {
        font-size: 0.8rem;
        padding: 2px 4px;
        margin-bottom: 2px;
        border-radius: 4px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        cursor: help;
    }
    .calendar-event.event { background-color: rgba(70, 130, 180, 0.7); color: white; }
    .calendar-event.holiday { background-color: rgba(211, 47, 47, 0.7); color: white; }
    .calendar-event.exam { background-color: rgba(255, 165, 0, 0.7); color: white; }

    .add-event-form {
        margin-top: 2rem;
        background: rgba(255,255,255,0.8);
        padding: 2rem;
        border-radius: 10px;
        border: 1px solid #ddd;
    }
    .add-event-form button { margin-right: 0.5rem; margin-top: 1rem; width: auto; }


    @media (max-width: 768px) {
        .logo h1 { font-size: 2rem; }
        .login-form { padding: 2rem; margin: 1rem; }
        .dashboard-header { flex-direction: column; gap: 1rem; text-align: center; }
        .dashboard-grid { grid-template-columns: 1fr; }
        .calendar-day { min-height: 60px; }
        .day-number { font-size: 1rem; }
        .calendar-event { font-size: 0.7rem; }
        .calendar-header { flex-direction: column; gap: 1rem;}
        .header-controls { margin-top: 1rem;}
    }

</style>

<div class="animated-bg">
    <div class="sphere"></div>
    <div class="sphere"></div>
    <div class="sphere"></div>
    <div class="sphere"></div>
    <div class="sphere"></div>
</div>

<div class="container">
    <div class="login-section" id="loginSection">
        <div class="logo">
            <h1>Fundación MOVAPE/UNICEP</h1>
            <p>Portal Universitario Digital</p>
        </div>

        <div class="login-form">
            <h2>🎓 Acceso al Portal</h2>
            <form id="loginForm" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="userType">Tipo de Usuario:</label>
                    <select id="userType" required>
                        <option value="">Selecciona tu tipo</option>
                        <option value="student">Estudiante</option>
                        <option value="professor">Docente</option>
                        <option value="admin">Administrador</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="userId">ID de Usuario:</label>
                    <input type="text" id="userId" placeholder="Ingresa tu ID universitario" required>
                </div>
                
                <button type="submit" class="login-btn">Ingresar al Portal</button>
            </form>
            
            <div class="error-message" id="errorMessage">
                ID o tipo de usuario no válido. Por favor verifica tu información.
            </div>
        </div>

        <div class="demo-ids">
            <h3>🔍 IDs de Demostración</h3>
            <div class="demo-id">
                <span>Admin de Sistema:</span>
                <span class="id-code" onclick="fillId('ADM-2024-001')">ADM-2024-001</span>
            </div>
            <div class="demo-id">
                <span>María González - Ing. Industrial:</span>
                <span class="id-code" onclick="fillId('EST-2024-001')">EST-2024-001</span>
            </div>
            <div class="demo-id">
                <span>Carlos Ruiz - Administración:</span>
                <span class="id-code" onclick="fillId('EST-2024-002')">EST-2024-002</span>
            </div>
            <div class="demo-id">
                <span>Ana Sofía - Psicología:</span>
                <span class="id-code" onclick="fillId('EST-2024-003')">EST-2024-003</span>
            </div>
            <div class="demo-id">
                <span>Docente Dr. Ana Mendoza:</span>
                <span class="id-code" onclick="fillId('PROF-2024-101')">PROF-2024-101</span>
            </div>
        </div>
    </div>

    <div class="dashboard-section" id="mainDashboard">
        <div class="dashboard-header">
            <h2 id="dashboardTitle">Dashboard</h2>
            <button class="back-btn" onclick="logout()">🚪 Cerrar Sesión</button>
        </div>

        <div class="dashboard-grid" id="dashboardContent">
        </div>
    </div>

    <div class="dashboard-section" id="detailedSection">
        <div class="dashboard-header">
            <h2 id="sectionTitle">Sección Detallada</h2>
            <div class="header-controls">
            </div>
            <button class="back-btn" onclick="backToDashboard()">🔙 Volver al Dashboard</button>
        </div>

        <div id="sectionContent">
        </div>
        
        <div id="calendar-event-form-container">
        </div>
    </div>
</div>

<script> 
    // --- DATA --- 
    let users = { 
        'EST-2024-001': { type: 'student', name: 'María González', career: 'Ingeniería Industrial', semester: '3° Cuatrimestre', modality: 'Sabatina', grades: [{ subject: 'Matemáticas Aplicadas', grade: '8.5' }, { subject: 'Procesos Industriales', grade: '9.2' }, { subject: 'Física General', grade: '7.8' }], schedule: [{ time: '08:00 - 10:00', subject: 'Matemáticas Aplicadas', room: 'Aula 201', professor: 'Prof. Dr. Ana Mendoza', day: 'Sábado' }, { time: '10:30 - 12:30', subject: 'Procesos Industriales', room: 'Lab. Industrial', professor: 'Prof. Ing. Ana Rodríguez', day: 'Sábado' }, { time: '14:00 - 16:00', subject: 'Física General', room: 'Aula 105', professor: 'Prof. Ing. Roberto Silva', day: 'Sábado' }] }, 
        'EST-2024-002': { type: 'student', name: 'Carlos Ruiz', career: 'Administración de Empresas', semester: '5° Cuatrimestre', modality: 'Dominical', grades: [{ subject: 'Marketing Digital', grade: '9.1' }, { subject: 'Contabilidad Avanzada', grade: '8.7' }], schedule: [{ time: '09:00 - 11:00', subject: 'Marketing Digital', room: 'Aula 301', professor: 'Prof. Lic. Patricia López', day: 'Domingo' }] }, 
        'EST-2024-003': { type: 'student', name: 'Ana Sofía Herrera', career: 'Psicología', semester: '4° Cuatrimestre', modality: 'Sabatina', grades: [{ subject: 'Psicología Cognitiva', grade: '9.3' }, { subject: 'Neuropsicología', grade: '8.8' }], schedule: [{ time: '08:00 - 10:00', subject: 'Psicología Cognitiva', room: 'Aula 301', professor: 'Prof. Dra. Carmen Vásquez', day: 'Sábado' }] }, 
        'PROF-2024-101': { type: 'professor', name: 'Dr. Ana Mendoza', department: 'Facultad de Ingeniería', subjects: ['Matemáticas Aplicadas', 'Cálculo Diferencial'], classes: [{ subject: 'Matemáticas Aplicadas', room: 'Aula 201', students: ['EST-2024-001', 'EST-2024-003'] }, { subject: 'Cálculo Diferencial', room: 'Aula 203', students: ['EST-2024-002', 'EST-2024-004'] }] }, 
        'PROF-2024-102': { type: 'professor', name: 'Ing. Roberto Silva', department: 'Facultad de Ciencias', subjects: ['Física General', 'Física Aplicada'], classes: [{ subject: 'Física General', room: 'Aula 105', students: ['EST-2024-001', 'EST-2024-005'] }, { subject: 'Física Aplicada', room: 'Lab. Física', students: ['EST-2024-001'] }] }, 
        'ADM-2024-001': { type: 'admin', name: 'Admin de Sistema', department: 'Administración Central', accessLevel: 'SuperUsuario' } 
    }; 
    
    let assignments = { 
        'Matemáticas Aplicadas': [{ title: 'Tarea 1: Derivadas', dueDate: '2025-10-15', submissions: { 'EST-2024-001': {status: 'Entregado', grade: null, feedback: ''}, 'EST-2024-003': {status: 'Pendiente', grade: null, feedback: ''} } }], 
        'Física General': [{ title: 'Reporte de Práctica 1', dueDate: '2025-10-20', submissions: { 'EST-2024-001': {status: 'Entregado', grade: 9.5, feedback: 'Excelente reporte, muy bien detallado.'}, 'EST-2024-005': {status: 'Pendiente', grade: null, feedback: ''} } }] 
    }; 

    // --- CALENDARIO MODIFICADO --- 
    let schoolCalendar = [ 
        { date: '2025-09-01', description: 'Inicio de Cuatrimestre Sep-Dic 2025', type: 'event' }, 
        { date: '2025-09-16', description: 'Día de la Independencia de México', type: 'holiday' }, 
        { date: '2025-10-12', description: 'Día de la Raza - Suspensión de clases', type: 'holiday' }, 
        { date: '2025-10-27', description: 'Inicio de Primer Parcial', type: 'exam' }, 
        { date: '2025-10-31', description: 'Entrega de Proyectos Finales (Tentativa)', type: 'event' }, 
        { date: '2025-11-02', description: 'Día de Muertos', type: 'holiday' }, 
        { date: '2025-11-20', description: 'Aniversario de la Revolución', type: 'holiday' }, 
        { date: '2025-12-08', description: 'Inicio de Segundo Parcial', type: 'exam' }, 
        { date: '2025-12-19', description: 'Fin de Cuatrimestre Sep-Dic 2025', type: 'event' }, 
    ]; 

    // --- GLOBAL STATE --- 
    let currentUserId = null; 
    let currentCalendarDate = new Date(2025, 9, 1); // Empezamos en Octubre de 2025 para la demo
    const TODAY_DATE = new Date(2025, 9, 27); // 27 de octubre de 2025 (Hardcoded para consistencia)

    // --- DOM ELEMENTS --- 
    const loginSection = document.getElementById('loginSection'); 
    const mainDashboard = document.getElementById('mainDashboard'); 
    const detailedSection = document.getElementById('detailedSection'); 
    const dashboardTitle = document.getElementById('dashboardTitle'); 
    const dashboardContent = document.getElementById('dashboardContent'); 
    const sectionTitle = document.getElementById('sectionTitle'); 
    const sectionContent = document.getElementById('sectionContent'); 
    const errorMessage = document.getElementById('errorMessage'); 
    const loginForm = document.getElementById('loginForm'); 
    const headerControls = document.querySelector('.header-controls'); 
    const calendarEventFormContainer = document.getElementById('calendar-event-form-container');

    // --- HELPER FUNCTIONS --- 
    function fillId(id) { 
        document.getElementById('userId').value = id; 
        if (id.startsWith('EST-')) document.getElementById('userType').value = 'student'; 
        else if (id.startsWith('PROF-')) document.getElementById('userType').value = 'professor'; 
        else if (id.startsWith('ADM-')) document.getElementById('userType').value = 'admin'; 
    } 

    function formatDate(date) { 
        const d = new Date(date); 
        const year = d.getFullYear(); 
        let month = '' + (d.getMonth() + 1); 
        let day = '' + d.getDate(); 
        if (month.length < 2) month = '0' + month; 
        if (day.length < 2) day = '0' + day; 
        return [year, month, day].join('-'); 
    } 

    // --- LOGIN & LOGOUT LOGIC --- 
    function handleLogin(event) { 
        event.preventDefault(); 
        const userIdInput = document.getElementById('userId').value; 
        const userTypeInput = document.getElementById('userType').value; 
        const user = users[userIdInput]; 

        if (user && user.type === userTypeInput) { 
            currentUserId = userIdInput; 
            loginSection.style.display = 'none'; 
            mainDashboard.style.display = 'flex'; 
            errorMessage.style.display = 'none'; 
            if (user.type === 'student') populateStudentDashboard(user); 
            else if (user.type === 'professor') populateProfessorDashboard(user); 
            else if (user.type === 'admin') populateAdminDashboard(user); 
        } else { 
            errorMessage.style.display = 'block'; 
        } 
    } 

    function logout() { 
        currentUserId = null; 
        loginSection.style.display = 'flex'; 
        mainDashboard.style.display = 'none'; 
        detailedSection.style.display = 'none'; 
        loginForm.reset(); 
        headerControls.innerHTML = ''; 
    } 

    // --- NAVIGATION --- 
    function backToDashboard() { 
        detailedSection.style.display = 'none'; 
        mainDashboard.style.display = 'flex'; 
        headerControls.innerHTML = ''; 
        calendarEventFormContainer.innerHTML = ''; // Limpiar el formulario de evento
        const user = users[currentUserId]; 
        if (user.type === 'student') populateStudentDashboard(user); 
        else if (user.type === 'professor') populateProfessorDashboard(user); 
        else if (user.type === 'admin') populateAdminDashboard(user); 
    } 

    // --- DASHBOARD POPULATION --- 
    function populateStudentDashboard(user) { 
        dashboardTitle.textContent = `Bienvenido, ${user.name}`; 
        dashboardContent.innerHTML = `
            <div class="dashboard-card non-clickable">
                <h3>🧑‍🎓 Info Estudiante</h3>
                <div class="card-content">
                    <p><strong>Carrera:</strong> ${user.career}</p>
                    <p><strong>Cuatrimestre:</strong> ${user.semester}</p>
                    <p><strong>Modalidad:</strong> ${user.modality}</p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('studentGrades')">
                <h3>📊 Mis Calificaciones</h3>
                <div class="card-content">
                    ${user.grades.map(g => `<div class="grade-item"><span>${g.subject}</span><span class="grade">${g.grade}</span></div>`).join('')}
                    <p style="margin-top: 1rem; text-align: right; font-weight: bold;">Ver todas...</p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('studentSchedule')">
                <h3>🗓️ Mi Horario</h3>
                <div class="card-content">
                    ${user.schedule.slice(0, 2).map(s => `<div class="schedule-item-summary"><span>${s.time}</span><span class="schedule-time">${s.subject}</span></div>`).join('')}
                    <p style="margin-top: 1rem; text-align: right; font-weight: bold;">Ver completo...</p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('studentAssignments')">
                <h3>📝 Tareas Pendientes</h3>
                <div class="card-content">
                    <p>Tienes **2 tareas pendientes** y **1 por calificar**.</p>
                    <p style="margin-top: 1rem; text-align: right; font-weight: bold;">Ver todas...</p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('schoolCalendar')">
                <h3>📅 Calendario Escolar</h3>
                <div class="card-content">
                    <p>Consulta fechas importantes del ciclo académico.</p>
                    ${schoolCalendar.filter(e => new Date(e.date) >= TODAY_DATE).slice(0, 3).map(e => `<div class="calendar-item ${e.type}"><strong>${e.date.slice(5)}:</strong> ${e.description}</div>`).join('')}
                </div>
            </div>
        `;
    } 

    function populateProfessorDashboard(user) { 
        dashboardTitle.textContent = `Bienvenido, ${user.name}`; 
        dashboardContent.innerHTML = `
            <div class="dashboard-card non-clickable">
                <h3>🧑‍🏫 Info Docente</h3>
                <div class="card-content">
                    <p><strong>Departamento:</strong> ${user.department}</p>
                    <p><strong>Clases Asignadas:</strong> ${user.subjects.length}</p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('professorClasses')">
                <h3>📚 Gestionar Clases</h3>
                <div class="card-content">
                    ${user.subjects.map(s => `<div class="subject-item"><span>${s}</span><span class="action-btn secondary" onclick="event.stopPropagation(); showDetailedView('classDetail', '${s}')">Ir a Clase</span></div>`).join('')}
                    <p style="margin-top: 1rem; text-align: right; font-weight: bold;">Seleccionar clase...</p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('professorMaterials')">
                <h3>📖 Material Académico</h3>
                <div class="card-content">
                    <p>Comparte y gestiona material de estudio con tus alumnos.</p>
                    <p style="margin-top: 1rem; text-align: center;"><button class="action-btn">Subir Material</button></p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('schoolCalendar')">
                <h3>📅 Calendario Escolar</h3>
                <div class="card-content">
                    <p>Consulta fechas importantes del ciclo académico.</p>
                    ${schoolCalendar.filter(e => new Date(e.date) >= TODAY_DATE).slice(0, 3).map(e => `<div class="calendar-item ${e.type}"><strong>${e.date.slice(5)}:</strong> ${e.description}</div>`).join('')}
                </div>
            </div>
        `;
    } 

    function populateAdminDashboard(user) { 
        dashboardTitle.textContent = `Panel de Administración, ${user.name}`; 
        dashboardContent.innerHTML = `
            <div class="dashboard-card non-clickable">
                <h3>🛡️ Info Admin</h3>
                <div class="card-content">
                    <p><strong>Nivel de Acceso:</strong> ${user.accessLevel}</p>
                    <p><strong>Departamento:</strong> ${user.department}</p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('adminUserManagement')">
                <h3>👥 Gestión de Usuarios</h3>
                <div class="card-content">
                    <p>Visualizar y modificar perfiles de estudiantes y docentes.</p>
                    <p style="margin-top: 1rem; text-align: center;"><button class="action-btn">Ir a Gestión</button></p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('schoolCalendar')">
                <h3>📅 Calendario Escolar (Gestión)</h3>
                <div class="card-content">
                    <p>Consulta y **edita** los eventos académicos principales.</p>
                    <p style="margin-top: 1rem; text-align: center;"><button class="action-btn">Abrir Calendario</button></p>
                </div>
            </div>

            <div class="dashboard-card" onclick="showDetailedView('adminLogs')">
                <h3>💻 Logs del Sistema</h3>
                <div class="card-content">
                    <p>Monitoreo de actividad y estado del portal.</p>
                    <p style="margin-top: 1rem; text-align: center;"><button class="action-btn secondary">Ver Registros</button></p>
                </div>
            </div>
        `;
    } 

    // --- DETAILED VIEW LOGIC --- 
    function showDetailedView(viewType, context) { 
        const user = users[currentUserId]; 
        if (!user) return; 
        mainDashboard.style.display = 'none'; 
        detailedSection.style.display = 'flex'; 
        sectionContent.innerHTML = ''; 
        headerControls.innerHTML = ''; 
        calendarEventFormContainer.innerHTML = ''; // Limpiar formulario al cambiar de vista

        switch (viewType) { 
            case 'schoolCalendar': 
                sectionTitle.textContent = '📅 Calendario Académico'; 
                if (user.type === 'admin') { 
                    headerControls.innerHTML = `<button class="action-btn" onclick="showAddEventForm()">➕ Añadir Evento</button>`; 
                } 
                currentCalendarDate = new Date(TODAY_DATE.getFullYear(), TODAY_DATE.getMonth(), 1); // Reset al mes actual de la demo
                renderCalendar(); 
                break; 
            case 'studentGrades': 
                sectionTitle.textContent = '📊 Mis Calificaciones'; 
                sectionContent.innerHTML = '<div class="dashboard-card non-clickable"><div class="card-content"><h2>Detalle de Calificaciones</h2><p>Aquí se listarán todas tus calificaciones por materia.</p></div></div>'; 
                break; 
            case 'studentSchedule': 
                sectionTitle.textContent = '🗓️ Mi Horario Completo'; 
                sectionContent.innerHTML = '<div class="dashboard-card non-clickable"><div class="card-content"><h2>Horario Semanal</h2><p>Aquí 
