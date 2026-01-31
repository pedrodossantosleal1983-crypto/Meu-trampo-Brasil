# Meu-trampo-Brasil
Para profissionais e empresa se conectar, acesso fácil e rápido.
Vou te dar o **código completo** para você copiar! 📋
Action: file_editor view /app/frontend/src/App.js
Observation: /app/frontend/src/App.js:
1|import { useState } from "react";
2|import "@/App.css";
3|import { BrowserRouter, Routes, Route, Link, useNavigate, useSearchParams } from "react-router-dom";
4|import { Phone, Briefcase, Users, Star, Check, Menu, X, MapPin, Mail, Clock, Send, Building2, User, Search, Filter, ChevronRight, Heart, Share2, MessageCircle } from "lucide-react";
5|
6|const PHONE_NUMBER = "+55 11 93074-3601";
7|const PHONE_WHATSAPP = "5511930743601";
8|
9|// Header Component
10|const Header = ({ isMenuOpen, setIsMenuOpen }) => {
11|  return (
12|    <header className="fixed top-0 left-0 right-0 bg-slate-900/95 backdrop-blur-md z-50 border-b border-emerald-500/20">
13|      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
14|        <div className="flex justify-between items-center h-16">
15|          <Link to="/" className="flex items-center gap-2">
16|            <Briefcase className="h-8 w-8 text-emerald-400" />
17|            <span className="text-xl font-bold text-white">Meu Trampo</span>
18|            <span className="text-emerald-400 text-sm font-medium">Brasil</span>
19|          </Link>
20|          
21|          {/* Desktop Navigation */}
22|          <nav className="hidden md:flex items-center gap-8">
23|            <Link to="/" className="text-gray-300 hover:text-emerald-400 transition-colors">Início</Link>
24|            <Link to="/vagas" className="text-gray-300 hover:text-emerald-400 transition-colors">Vagas</Link>
25|            <Link to="/empresas" className="text-gray-300 hover:text-emerald-400 transition-colors">Empresas</Link>
26|            <Link to="/contato" className="text-gray-300 hover:text-emerald-400 transition-colors">Contato</Link>
27|            <a href={`tel:${PHONE_NUMBER}`} className="flex items-center gap-2 text-emerald-400 hover:text-emerald-300 transition-colors" data-testid="header-phone">
28|              <Phone className="h-4 w-4" />
29|              <span className="text-sm font-medium">{PHONE_NUMBER}</span>
30|            </a>
31|          </nav>
32|
33|          <div className="hidden md:flex items-center gap-4">
34|            <Link to="/login" className="text-gray-300 hover:text-white transition-colors" data-testid="login-btn">Entrar</Link>
35|            <Link to="/register" className="bg-emerald-500 hover:bg-emerald-600 text-white px-4 py-2 rounded-full font-medium transition-colors" data-testid="register-btn">
36|              Cadastre-se
37|            </Link>
38|          </div>
39|
40|          {/* Mobile Menu Button */}
41|          <button 
42|            className="md:hidden text-white p-2"
43|            onClick={() => setIsMenuOpen(!isMenuOpen)}
44|            data-testid="mobile-menu-btn"
45|          >
46|            {isMenuOpen ? <X className="h-6 w-6" /> : <Menu className="h-6 w-6" />}
47|          </button>
48|        </div>
49|
50|        {/* Mobile Menu */}
51|        {isMenuOpen && (
52|          <div className="md:hidden py-4 border-t border-emerald-500/20">
53|            <nav className="flex flex-col gap-4">
54|              <Link to="/" className="text-gray-300 hover:text-emerald-400 transition-colors">Início</Link>
55|              <Link to="/vagas" className="text-gray-300 hover:text-emerald-400 transition-colors">Vagas</Link>
56|              <Link to="/empresas" className="text-gray-300 hover:text-emerald-400 transition-colors">Empresas</Link>
57|              <Link to="/contato" className="text-gray-300 hover:text-emerald-400 transition-colors">Contato</Link>
58|              <a href={`tel:${PHONE_NUMBER}`} className="flex items-center gap-2 text-emerald-400" data-testid="mobile-phone">
59|                <Phone className="h-4 w-4" />
60|                <span>{PHONE_NUMBER}</span>
61|              </a>
62|              <div className="flex gap-4 pt-4 border-t border-emerald-500/20">
63|                <Link to="/login" className="text-gray-300 hover:text-white transition-colors">Entrar</Link>
64|                <Link to="/register" className="bg-emerald-500 hover:bg-emerald-600 text-white px-4 py-2 rounded-full font-medium transition-colors">
65|                  Cadastre-se
66|                </Link>
67|              </div>
68|            </nav>
69|          </div>
70|        )}
71|      </div>
72|    </header>
73|  );
74|};
75|
76|// Footer Component
77|const Footer = () => {
78|  return (
79|    <footer className="bg-slate-900 border-t border-emerald-500/20">
80|      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
81|        <div className="grid grid-cols-1 md:grid-cols-4 gap-8">
82|          {/* Brand */}
83|          <div className="col-span-1 md:col-span-2">
84|            <div className="flex items-center gap-2 mb-4">
85|              <Briefcase className="h-8 w-8 text-emerald-400" />
86|              <span className="text-xl font-bold text-white">Meu Trampo</span>
87|              <span className="text-emerald-400 text-sm font-medium">Brasil</span>
88|            </div>
89|            <p className="text-gray-400 mb-4">
90|              A plataforma inteligente que conecta talentos brasileiros às melhores oportunidades de trabalho.
91|            </p>
92|            <div className="flex flex-col gap-2">
93|              <a href={`tel:${PHONE_NUMBER}`} className="flex items-center gap-2 text-emerald-400 hover:text-emerald-300 transition-colors" data-testid="footer-phone">
94|                <Phone className="h-5 w-5" />
95|                <span className="font-medium">{PHONE_NUMBER}</span>
96|              </a>
97|              <a href={`https://wa.me/${PHONE_WHATSAPP}`} target="_blank" rel="noopener noreferrer" className="flex items-center gap-2 text-emerald-400 hover:text-emerald-300 transition-colors" data-testid="footer-whatsapp">
98|                <MessageCircle className="h-5 w-5" />
99|                <span>WhatsApp: {PHONE_NUMBER}</span>
100|              </a>
101|              <a href="mailto:contato@meutrampo.com.br" className="flex items-center gap-2 text-gray-400 hover:text-emerald-400 transition-colors">
102|                <Mail className="h-5 w-5" />
103|                <span>contato@meutrampo.com.br</span>
104|              </a>
105|            </div>
106|          </div>
107|
108|          {/* Links */}
109|          <div>
110|            <h3 className="text-white font-semibold mb-4">Para Candidatos</h3>
111|            <ul className="space-y-2">
112|              <li><Link to="/vagas" className="text-gray-400 hover:text-emerald-400 transition-colors">Buscar Vagas</Link></li>
113|              <li><Link to="/register?type=candidate" className="text-gray-400 hover:text-emerald-400 transition-colors">Criar Currículo</Link></li>
114|              <li><Link to="/premium" className="text-gray-400 hover:text-emerald-400 transition-colors">Planos Premium</Link></li>
115|            </ul>
116|          </div>
117|
118|          <div>
119|            <h3 className="text-white font-semibold mb-4">Para Empresas</h3>
120|            <ul className="space-y-2">
121|              <li><Link to="/register?type=company" className="text-gray-400 hover:text-emerald-400 transition-colors">Publicar Vagas</Link></li>
122|              <li><Link to="/empresas" className="text-gray-400 hover:text-emerald-400 transition-colors">Buscar Talentos</Link></li>
123|              <li><Link to="/contato" className="text-gray-400 hover:text-emerald-400 transition-colors">Fale Conosco</Link></li>
124|            </ul>
125|          </div>
126|        </div>
127|
128|        <div className="border-t border-emerald-500/20 mt-8 pt-8 flex flex-col md:flex-row justify-between items-center gap-4">
129|          <p className="text-gray-400 text-sm">
130|            © 2024 Meu Trampo Brasil. Todos os direitos reservados.
131|          </p>
132|          <div className="flex items-center gap-2 text-gray-400 text-sm">
133|            <Phone className="h-4 w-4 text-emerald-400" />
134|            <span>Atendimento: {PHONE_NUMBER}</span>
135|          </div>
136|        </div>
137|      </div>
138|    </footer>
139|  );
140|};
141|
142|// WhatsApp Floating Button
143|const WhatsAppButton = () => {
144|  return (
145|    <a
146|      href={`https://wa.me/${PHONE_WHATSAPP}?text=Olá! Vim pelo site Meu Trampo Brasil e gostaria de mais informações.`}
147|      target="_blank"
148|      rel="noopener noreferrer"
149|      className="fixed bottom-6 right-6 bg-green-500 hover:bg-green-600 text-white p-4 rounded-full shadow-lg hover:shadow-xl transition-all z-50 group"
150|      data-testid="whatsapp-float-btn"
151|    >
152|      <MessageCircle className="h-6 w-6" />
153|      <span className="absolute right-full mr-3 top-1/2 -translate-y-1/2 bg-slate-800 text-white px-3 py-2 rounded-lg text-sm whitespace-nowrap opacity-0 group-hover:opacity-100 transition-opacity">
154|        Fale conosco: {PHONE_NUMBER}
155|      </span>
156|    </a>
157|  );
158|};
159|
160|// Home Page
161|const Home = () => {
162|  const navigate = useNavigate();
163|
164|  const featuredJobs = [
165|    { id: 1, title: "Desenvolvedor Full Stack", company: "Tech Solutions", location: "São Paulo, SP", salary: "R$ 8.000 - R$ 12.000", type: "CLT", posted: "2 dias atrás" },
166|    { id: 2, title: "Designer UX/UI", company: "Creative Agency", location: "Rio de Janeiro, RJ", salary: "R$ 6.000 - R$ 9.000", type: "PJ", posted: "1 dia atrás" },
167|    { id: 3, title: "Analista de Marketing", company: "E-commerce Brasil", location: "Remoto", salary: "R$ 5.000 - R$ 7.000", type: "CLT", posted: "3 dias atrás" },
168|    { id: 4, title: "Gerente de Projetos", company: "Consultoria ABC", location: "Belo Horizonte, MG", salary: "R$ 10.000 - R$ 15.000", type: "CLT", posted: "5 horas atrás" },
169|  ];
170|
171|  return (
172|    <div className="min-h-screen bg-slate-950">
173|      {/* Hero Section */}
174|      <section className="pt-24 pb-16 px-4 bg-gradient-to-br from-slate-900 via-slate-950 to-emerald-950">
175|        <div className="max-w-7xl mx-auto">
176|          <div className="grid md:grid-cols-2 gap-12 items-center">
177|            <div>
178|              <h1 className="text-4xl md:text-5xl lg:text-6xl font-bold text-white mb-6 leading-tight">
179|                Encontre o <span className="text-emerald-400">Trampo Ideal</span> para Você
180|              </h1>
181|              <p className="text-xl text-gray-300 mb-8">
182|                A plataforma inteligente que conecta talentos brasileiros às melhores oportunidades de trabalho
183|              </p>
184|              
185|              {/* Search Bar */}
186|              <div className="bg-slate-800/50 backdrop-blur-sm p-2 rounded-2xl border border-emerald-500/20 mb-6">
187|                <div className="flex flex-col md:flex-row gap-2">
188|                  <div className="flex-1 flex items-center gap-2 bg-slate-900 rounded-xl px-4 py-3">
189|                    <Search className="h-5 w-5 text-gray-400" />
190|                    <input 
191|                      type="text" 
192|                      placeholder="Cargo, empresa ou palavra-chave"
193|                      className="bg-transparent text-white placeholder-gray-400 outline-none w-full"
194|                      data-testid="search-input"
195|                    />
196|                  </div>
197|                  <div className="flex-1 flex items-center gap-2 bg-slate-900 rounded-xl px-4 py-3">
198|                    <MapPin className="h-5 w-5 text-gray-400" />
199|                    <input 
200|                      type="text" 
201|                      placeholder="Cidade ou estado"
202|                      className="bg-transparent text-white placeholder-gray-400 outline-none w-full"
203|                      data-testid="location-input"
204|                    />
205|                  </div>
206|                  <button 
207|                    onClick={() => navigate('/vagas')}
208|                    className="bg-emerald-500 hover:bg-emerald-600 text-white px-8 py-3 rounded-xl font-semibold transition-colors"
209|                    data-testid="search-btn"
210|                  >
211|                    Buscar
212|                  </button>
213|                </div>
214|              </div>
215|
216|              <div className="flex flex-wrap gap-4">
217|                <button 
218|                  onClick={() => navigate('/register?type=candidate')}
219|                  className="bg-emerald-500 hover:bg-emerald-600 text-white px-6 py-3 rounded-full font-semibold transition-colors flex items-center gap-2"
220|                  data-testid="candidate-register-btn"
221|                >
222|                  <User className="h-5 w-5" />
223|                  Buscar Vagas
224|                </button>
225|                <button 
226|                  onClick={() => navigate('/register?type=company')}
227|                  className="bg-slate-800 hover:bg-slate-700 text-white px-6 py-3 rounded-full font-semibold transition-colors border border-emerald-500/30 flex items-center gap-2"
228|                  data-testid="company-register-btn"
229|                >
230|                  <Building2 className="h-5 w-5" />
231|                  Publicar Vagas
232|                </button>
233|              </div>
234|
235|              {/* Contact Info */}
236|              <div className="mt-8 p-4 bg-slate-800/30 rounded-xl border border-emerald-500/20">
237|                <p className="text-gray-400 text-sm mb-2">Precisa de ajuda? Fale conosco:</p>
238|                <a href={`tel:${PHONE_NUMBER}`} className="flex items-center gap-2 text-emerald-400 hover:text-emerald-300 font-medium" data-testid="hero-phone">
239|                  <Phone className="h-5 w-5" />
240|                  {PHONE_NUMBER}
241|                </a>
242|              </div>
243|            </div>
244|
245|            <div className="hidden md:block">
246|              <img 
247|                src="https://images.unsplash.com/photo-1521737711867-e3b97375f902?w=600&h=500&fit=crop"
248|                alt="Profissionais trabalhando"
249|                className="rounded-2xl shadow-2xl border border-emerald-500/20"
250|              />
251|            </div>
252|          </div>
253|        </div>
254|      </section>
255|
256|      {/* Stats Section */}
257|      <section className="py-12 bg-slate-900 border-y border-emerald-500/20">
258|        <div className="max-w-7xl mx-auto px-4">
259|          <div className="grid grid-cols-2 md:grid-cols-4 gap-8">
260|            <div className="text-center">
261|              <div className="text-3xl md:text-4xl font-bold text-emerald-400 mb-2">5.000+</div>
262|              <div className="text-gray-400">Vagas Ativas</div>
263|            </div>
264|            <div className="text-center">
265|              <div className="text-3xl md:text-4xl font-bold text-emerald-400 mb-2">10.000+</div>
266|              <div className="text-gray-400">Candidatos</div>
267|            </div>
268|            <div className="text-center">
269|              <div className="text-3xl md:text-4xl font-bold text-emerald-400 mb-2">500+</div>
270|              <div className="text-gray-400">Empresas</div>
271|            </div>
272|            <div className="text-center">
273|              <div className="text-3xl md:text-4xl font-bold text-emerald-400 mb-2">95%</div>
274|              <div className="text-gray-400">Satisfação</div>
275|            </div>
276|          </div>
277|        </div>
278|      </section>
279|
280|      {/* Features Section */}
281|      <section className="py-16 px-4">
282|        <div className="max-w-7xl mx-auto">
283|          <h2 className="text-3xl md:text-4xl font-bold text-white text-center mb-12">
284|            Por que escolher o <span className="text-emerald-400">Meu Trampo</span>?
285|          </h2>
286|          
287|          <div className="grid md:grid-cols-3 gap-8">
288|            <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20 hover:border-emerald-500/40 transition-colors">
289|              <div className="w-14 h-14 bg-emerald-500/20 rounded-xl flex items-center justify-center mb-6">
290|                <Briefcase className="h-7 w-7 text-emerald-400" />
291|              </div>
292|              <h3 className="text-xl font-semibold text-white mb-3">Milhares de Vagas</h3>
293|              <p className="text-gray-400">Acesse oportunidades em todas as áreas e níveis de experiência em todo o Brasil.</p>
294|            </div>
295|
296|            <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20 hover:border-emerald-500/40 transition-colors">
297|              <div className="w-14 h-14 bg-emerald-500/20 rounded-xl flex items-center justify-center mb-6">
298|                <Star className="h-7 w-7 text-emerald-400" />
299|              </div>
300|              <h3 className="text-xl font-semibold text-white mb-3">Match Inteligente</h3>
301|              <p className="text-gray-400">Algoritmos que conectam você às vagas perfeitas para seu perfil profissional.</p>
302|            </div>
303|
304|            <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20 hover:border-emerald-500/40 transition-colors">
305|              <div className="w-14 h-14 bg-emerald-500/20 rounded-xl flex items-center justify-center mb-6">
306|                <Users className="h-7 w-7 text-emerald-400" />
307|              </div>
308|              <h3 className="text-xl font-semibold text-white mb-3">Suporte Dedicado</h3>
309|              <p className="text-gray-400">Equipe pronta para ajudar. Ligue: <a href={`tel:${PHONE_NUMBER}`} className="text-emerald-400">{PHONE_NUMBER}</a></p>
310|            </div>
311|          </div>
312|        </div>
313|      </section>
314|
315|      {/* Featured Jobs */}
316|      <section className="py-16 px-4 bg-slate-900/50">
317|        <div className="max-w-7xl mx-auto">
318|          <div className="flex justify-between items-center mb-8">
319|            <h2 className="text-3xl font-bold text-white">Vagas em Destaque</h2>
320|            <Link to="/vagas" className="text-emerald-400 hover:text-emerald-300 flex items-center gap-1">
321|              Ver todas <ChevronRight className="h-4 w-4" />
322|            </Link>
323|          </div>
324|
325|          <div className="grid md:grid-cols-2 gap-6">
326|            {featuredJobs.map(job => (
327|              <div key={job.id} className="bg-slate-900 p-6 rounded-xl border border-emerald-500/20 hover:border-emerald-500/40 transition-all hover:shadow-lg hover:shadow-emerald-500/10">
328|                <div className="flex justify-between items-start mb-4">
329|                  <div>
330|                    <h3 className="text-xl font-semibold text-white mb-1">{job.title}</h3>
331|                    <p className="text-emerald-400">{job.company}</p>
332|                  </div>
333|                  <button className="text-gray-400 hover:text-red-400 transition-colors">
334|                    <Heart className="h-5 w-5" />
335|                  </button>
336|                </div>
337|                <div className="flex flex-wrap gap-4 text-sm text-gray-400 mb-4">
338|                  <span className="flex items-center gap-1">
339|                    <MapPin className="h-4 w-4" /> {job.location}
340|                  </span>
341|                  <span className="flex items-center gap-1">
342|                    <Briefcase className="h-4 w-4" /> {job.type}
343|                  </span>
344|                  <span className="flex items-center gap-1">
345|                    <Clock className="h-4 w-4" /> {job.posted}
346|                  </span>
347|                </div>
348|                <div className="flex justify-between items-center">
349|                  <span className="text-emerald-400 font-semibold">{job.salary}</span>
350|                  <button className="bg-emerald-500/20 hover:bg-emerald-500 text-emerald-400 hover:text-white px-4 py-2 rounded-lg transition-colors">
351|                    Candidatar-se
352|                  </button>
353|                </div>
354|              </div>
355|            ))}
356|          </div>
357|        </div>
358|      </section>
359|
360|      {/* Premium Plans */}
361|      <section className="py-16 px-4">
362|        <div className="max-w-7xl mx-auto">
363|          <h2 className="text-3xl md:text-4xl font-bold text-white text-center mb-4">
364|            Planos <span className="text-emerald-400">Premium</span>
365|          </h2>
366|          <p className="text-gray-400 text-center mb-12">Destaque-se da concorrência</p>
367|
368|          <div className="grid md:grid-cols-3 gap-8">
369|            <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20">
370|              <h3 className="text-xl font-semibold text-white mb-2">Acesso Vitalício</h3>
371|              <div className="text-3xl font-bold text-emerald-400 mb-1">R$ 19,99</div>
372|              <p className="text-gray-400 text-sm mb-6">pagamento único</p>
373|              <ul className="space-y-3 mb-8">
374|                <li className="flex items-center gap-2 text-gray-300">
375|                  <Check className="h-5 w-5 text-emerald-400" />
376|                  Acesso ilimitado a todas as vagas
377|                </li>
378|                <li className="flex items-center gap-2 text-gray-300">
379|                  <Check className="h-5 w-5 text-emerald-400" />
380|                  Candidaturas ilimitadas
381|                </li>
382|                <li className="flex items-center gap-2 text-gray-300">
383|                  <Check className="h-5 w-5 text-emerald-400" />
384|                  Destaque no perfil
385|                </li>
386|              </ul>
387|              <button className="w-full bg-slate-800 hover:bg-emerald-500 text-white py-3 rounded-xl font-semibold transition-colors" data-testid="plan-lifetime-btn">
388|                Adquirir Agora
389|              </button>
390|            </div>
391|
392|            <div className="bg-slate-900 p-8 rounded-2xl border-2 border-emerald-500 relative">
393|              <div className="absolute -top-4 left-1/2 -translate-x-1/2 bg-emerald-500 text-white px-4 py-1 rounded-full text-sm font-medium">
394|                Mais Popular
395|              </div>
396|              <h3 className="text-xl font-semibold text-white mb-2">Fura Fila</h3>
397|              <div className="text-3xl font-bold text-emerald-400 mb-1">R$ 14,99</div>
398|              <p className="text-gray-400 text-sm mb-6">por candidatura</p>
399|              <ul className="space-y-3 mb-8">
400|                <li className="flex items-center gap-2 text-gray-300">
401|                  <Check className="h-5 w-5 text-emerald-400" />
402|                  Apareça no topo das candidaturas
403|                </li>
404|                <li className="flex items-center gap-2 text-gray-300">
405|                  <Check className="h-5 w-5 text-emerald-400" />
406|                  Destaque para empresas
407|                </li>
408|                <li className="flex items-center gap-2 text-gray-300">
409|                  <Check className="h-5 w-5 text-emerald-400" />
410|                  Prioridade nas seleções
411|                </li>
412|              </ul>
413|              <button className="w-full bg-emerald-500 hover:bg-emerald-600 text-white py-3 rounded-xl font-semibold transition-colors" data-testid="plan-priority-btn">
414|                Adquirir Agora
415|              </button>
416|            </div>
417|
418|            <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20">
419|              <h3 className="text-xl font-semibold text-white mb-2">Perfil Ideal</h3>
420|              <div className="text-3xl font-bold text-emerald-400 mb-1">R$ 100,00</div>
421|              <p className="text-gray-400 text-sm mb-6">análise completa</p>
422|              <ul className="space-y-3 mb-8">
423|                <li className="flex items-center gap-2 text-gray-300">
424|                  <Check className="h-5 w-5 text-emerald-400" />
425|                  Análise de compatibilidade
426|                </li>
427|                <li className="flex items-center gap-2 text-gray-300">
428|                  <Check className="h-5 w-5 text-emerald-400" />
429|                  Veja se você é o candidato ideal
430|                </li>
431|                <li className="flex items-center gap-2 text-gray-300">
432|                  <Check className="h-5 w-5 text-emerald-400" />
433|                  Economize tempo
434|                </li>
435|              </ul>
436|              <button className="w-full bg-slate-800 hover:bg-emerald-500 text-white py-3 rounded-xl font-semibold transition-colors" data-testid="plan-analysis-btn">
437|                Adquirir Agora
438|              </button>
439|            </div>
440|          </div>
441|        </div>
442|      </section>
443|
444|      {/* CTA Section */}
445|      <section className="py-16 px-4 bg-gradient-to-r from-emerald-600 to-emerald-500">
446|        <div className="max-w-4xl mx-auto text-center">
447|          <h2 className="text-3xl md:text-4xl font-bold text-white mb-4">
448|            Pronto para encontrar seu próximo trampo?
449|          </h2>
450|          <p className="text-emerald-100 text-lg mb-8">
451|            Cadastre-se gratuitamente e comece a receber oportunidades hoje mesmo!
452|          </p>
453|          <div className="flex flex-col sm:flex-row gap-4 justify-center items-center">
454|            <Link to="/register" className="bg-white text-emerald-600 px-8 py-3 rounded-full font-semibold hover:bg-emerald-50 transition-colors">
455|              Começar Agora
456|            </Link>
457|            <a href={`tel:${PHONE_NUMBER}`} className="text-white flex items-center gap-2 hover:text-emerald-100 transition-colors" data-testid="cta-phone">
458|              <Phone className="h-5 w-5" />
459|              Ligue: {PHONE_NUMBER}
460|            </a>
461|          </div>
462|        </div>
463|      </section>
464|    </div>
465|  );
466|};
467|
468|// Jobs Page
469|const Jobs = () => {
470|  const [searchTerm, setSearchTerm] = useState("");
471|  
472|  const jobs = [
473|    { id: 1, title: "Desenvolvedor Full Stack", company: "Tech Solutions", location: "São Paulo, SP", salary: "R$ 8.000 - R$ 12.000", type: "CLT", posted: "2 dias atrás", description: "Desenvolvimento de aplicações web com React e Node.js" },
474|    { id: 2, title: "Designer UX/UI", company: "Creative Agency", location: "Rio de Janeiro, RJ", salary: "R$ 6.000 - R$ 9.000", type: "PJ", posted: "1 dia atrás", description: "Criação de interfaces modernas e experiências de usuário" },
475|    { id: 3, title: "Analista de Marketing", company: "E-commerce Brasil", location: "Remoto", salary: "R$ 5.000 - R$ 7.000", type: "CLT", posted: "3 dias atrás", description: "Gestão de campanhas digitais e análise de métricas" },
476|    { id: 4, title: "Gerente de Projetos", company: "Consultoria ABC", location: "Belo Horizonte, MG", salary: "R$ 10.000 - R$ 15.000", type: "CLT", posted: "5 horas atrás", description: "Coordenação de projetos de TI e gestão de equipes" },
477|    { id: 5, title: "Desenvolvedor Mobile", company: "App Masters", location: "Curitiba, PR", salary: "R$ 7.000 - R$ 11.000", type: "CLT", posted: "1 dia atrás", description: "Desenvolvimento de apps iOS e Android com React Native" },
478|    { id: 6, title: "Analista de Dados", company: "Data Insights", location: "Remoto", salary: "R$ 8.000 - R$ 13.000", type: "PJ", posted: "4 horas atrás", description: "Análise de dados e criação de dashboards" },
479|  ];
480|
481|  return (
482|    <div className="min-h-screen bg-slate-950 pt-24">
483|      <div className="max-w-7xl mx-auto px-4 py-8">
484|        <div className="flex flex-col md:flex-row justify-between items-start md:items-center gap-4 mb-8">
485|          <div>
486|            <h1 className="text-3xl font-bold text-white mb-2">Vagas Disponíveis</h1>
487|            <p className="text-gray-400">Encontre a oportunidade perfeita para você</p>
488|          </div>
489|          <a href={`tel:${PHONE_NUMBER}`} className="flex items-center gap-2 text-emerald-400 hover:text-emerald-300" data-testid="jobs-phone">
490|            <Phone className="h-5 w-5" />
491|            Dúvidas? {PHONE_NUMBER}
492|          </a>
493|        </div>
494|
495|        {/* Search */}
496|        <div className="bg-slate-900 p-4 rounded-xl border border-emerald-500/20 mb-8">
497|          <div className="flex flex-col md:flex-row gap-4">
498|            <div className="flex-1 flex items-center gap-2 bg-slate-800 rounded-lg px-4 py-3">
499|              <Search className="h-5 w-5 text-gray-400" />
500|              <input 
501|                type="text"
502|                value={searchTerm}
503|                onChange={(e) => setSearchTerm(e.target.value)}
504|                placeholder="Buscar vagas..."
505|                className="bg-transparent text-white placeholder-gray-400 outline-none w-full"
506|                data-testid="jobs-search-input"
507|              />
508|            </div>
509|            <button className="flex items-center gap-2 bg-slate-800 hover:bg-slate-700 text-white px-4 py-3 rounded-lg transition-colors">
510|              <Filter className="h-5 w-5" />
511|              Filtros
512|            </button>
513|          </div>
514|        </div>
515|
516|        {/* Jobs List */}
517|        <div className="space-y-4">
518|          {jobs.map(job => (
519|            <div key={job.id} className="bg-slate-900 p-6 rounded-xl border border-emerald-500/20 hover:border-emerald-500/40 transition-all">
520|              <div className="flex flex-col md:flex-row justify-between gap-4">
521|                <div className="flex-1">
522|                  <div className="flex items-start justify-between">
523|                    <div>
524|                      <h3 className="text-xl font-semibold text-white mb-1">{job.title}</h3>
525|                      <p className="text-emerald-400 mb-2">{job.company}</p>
526|                    </div>
527|                    <div className="flex gap-2">
528|                      <button className="text-gray-400 hover:text-red-400 transition-colors">
529|                        <Heart className="h-5 w-5" />
530|                      </button>
531|                      <button className="text-gray-400 hover:text-emerald-400 transition-colors">
532|                        <Share2 className="h-5 w-5" />
533|                      </button>
534|                    </div>
535|                  </div>
536|                  <p className="text-gray-400 mb-4">{job.description}</p>
537|                  <div className="flex flex-wrap gap-4 text-sm text-gray-400">
538|                    <span className="flex items-center gap-1">
539|                      <MapPin className="h-4 w-4" /> {job.location}
540|                    </span>
541|                    <span className="flex items-center gap-1">
542|                      <Briefcase className="h-4 w-4" /> {job.type}
543|                    </span>
544|                    <span className="flex items-center gap-1">
545|                      <Clock className="h-4 w-4" /> {job.posted}
546|                    </span>
547|                  </div>
548|                </div>
549|                <div className="flex flex-col items-end justify-between">
550|                  <span className="text-emerald-400 font-semibold text-lg">{job.salary}</span>
551|                  <button className="bg-emerald-500 hover:bg-emerald-600 text-white px-6 py-2 rounded-lg transition-colors mt-4">
552|                    Candidatar-se
553|                  </button>
554|                </div>
555|              </div>
556|            </div>
557|          ))}
558|        </div>
559|      </div>
560|    </div>
561|  );
562|};
563|
564|// Companies Page
565|const Companies = () => {
566|  const companies = [
567|    { id: 1, name: "Tech Solutions", industry: "Tecnologia", jobs: 12, location: "São Paulo, SP", logo: "TS" },
568|    { id: 2, name: "Creative Agency", industry: "Marketing", jobs: 5, location: "Rio de Janeiro, RJ", logo: "CA" },
569|    { id: 3, name: "E-commerce Brasil", industry: "E-commerce", jobs: 8, location: "São Paulo, SP", logo: "EB" },
570|    { id: 4, name: "Consultoria ABC", industry: "Consultoria", jobs: 3, location: "Belo Horizonte, MG", logo: "AB" },
571|    { id: 5, name: "App Masters", industry: "Tecnologia", jobs: 7, location: "Curitiba, PR", logo: "AM" },
572|    { id: 6, name: "Data Insights", industry: "Dados", jobs: 4, location: "Remoto", logo: "DI" },
573|  ];
574|
575|  return (
576|    <div className="min-h-screen bg-slate-950 pt-24">
577|      <div className="max-w-7xl mx-auto px-4 py-8">
578|        <div className="flex flex-col md:flex-row justify-between items-start md:items-center gap-4 mb-8">
579|          <div>
580|            <h1 className="text-3xl font-bold text-white mb-2">Empresas Parceiras</h1>
581|            <p className="text-gray-400">Conheça as empresas que confiam no Meu Trampo Brasil</p>
582|          </div>
583|          <a href={`tel:${PHONE_NUMBER}`} className="flex items-center gap-2 text-emerald-400 hover:text-emerald-300" data-testid="companies-phone">
584|            <Phone className="h-5 w-5" />
585|            Seja parceiro: {PHONE_NUMBER}
586|          </a>
587|        </div>
588|
589|        <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
590|          {companies.map(company => (
591|            <div key={company.id} className="bg-slate-900 p-6 rounded-xl border border-emerald-500/20 hover:border-emerald-500/40 transition-all">
592|              <div className="flex items-center gap-4 mb-4">
593|                <div className="w-16 h-16 bg-emerald-500/20 rounded-xl flex items-center justify-center text-emerald-400 font-bold text-xl">
594|                  {company.logo}
595|                </div>
596|                <div>
597|                  <h3 className="text-xl font-semibold text-white">{company.name}</h3>
598|                  <p className="text-gray-400">{company.industry}</p>
599|                </div>
600|              </div>
601|              <div className="flex items-center justify-between text-sm">
602|                <span className="text-gray-400 flex items-center gap-1">
603|                  <MapPin className="h-4 w-4" /> {company.location}
604|                </span>
605|                <span className="text-emerald-400 font-medium">{company.jobs} vagas</span>
606|              </div>
607|              <button className="w-full mt-4 bg-slate-800 hover:bg-emerald-500 text-white py-2 rounded-lg transition-colors">
608|                Ver Vagas
609|              </button>
610|            </div>
611|          ))}
612|        </div>
613|      </div>
614|    </div>
615|  );
616|};
617|
618|// Contact Page
619|const Contact = () => {
620|  const [formData, setFormData] = useState({
621|    name: "",
622|    email: "",
623|    phone: "",
624|    subject: "",
625|    message: ""
626|  });
627|
628|  const handleSubmit = (e) => {
629|    e.preventDefault();
630|    alert("Mensagem enviada com sucesso! Entraremos em contato em breve.");
631|  };
632|
633|  return (
634|    <div className="min-h-screen bg-slate-950 pt-24">
635|      <div className="max-w-7xl mx-auto px-4 py-8">
636|        <div className="text-center mb-12">
637|          <h1 className="text-3xl md:text-4xl font-bold text-white mb-4">Entre em Contato</h1>
638|          <p className="text-gray-400 text-lg">Estamos aqui para ajudar você</p>
639|        </div>
640|
641|        <div className="grid md:grid-cols-2 gap-12">
642|          {/* Contact Info */}
643|          <div>
644|            <h2 className="text-2xl font-semibold text-white mb-6">Informações de Contato</h2>
645|            
646|            <div className="space-y-6">
647|              <div className="bg-slate-900 p-6 rounded-xl border border-emerald-500/20">
648|                <div className="flex items-center gap-4">
649|                  <div className="w-12 h-12 bg-emerald-500/20 rounded-xl flex items-center justify-center">
650|                    <Phone className="h-6 w-6 text-emerald-400" />
651|                  </div>
652|                  <div>
653|                    <h3 className="text-white font-medium">Telefone</h3>
654|                    <a href={`tel:${PHONE_NUMBER}`} className="text-emerald-400 hover:text-emerald-300 text-lg font-semibold" data-testid="contact-phone">
655|                      {PHONE_NUMBER}
656|                    </a>
657|                  </div>
658|                </div>
659|              </div>
660|
661|              <div className="bg-slate-900 p-6 rounded-xl border border-emerald-500/20">
662|                <div className="flex items-center gap-4">
663|                  <div className="w-12 h-12 bg-green-500/20 rounded-xl flex items-center justify-center">
664|                    <MessageCircle className="h-6 w-6 text-green-400" />
665|                  </div>
666|                  <div>
667|                    <h3 className="text-white font-medium">WhatsApp</h3>
668|                    <a 
669|                      href={`https://wa.me/${PHONE_WHATSAPP}`} 
670|                      target="_blank" 
671|                      rel="noopener noreferrer"
672|                      className="text-green-400 hover:text-green-300 text-lg font-semibold"
673|                      data-testid="contact-whatsapp"
674|                    >
675|                      {PHONE_NUMBER}
676|                    </a>
677|                  </div>
678|                </div>
679|              </div>
680|
681|              <div className="bg-slate-900 p-6 rounded-xl border border-emerald-500/20">
682|                <div className="flex items-center gap-4">
683|                  <div className="w-12 h-12 bg-emerald-500/20 rounded-xl flex items-center justify-center">
684|                    <Mail className="h-6 w-6 text-emerald-400" />
685|                  </div>
686|                  <div>
687|                    <h3 className="text-white font-medium">E-mail</h3>
688|                    <a href="mailto:contato@meutrampo.com.br" className="text-emerald-400 hover:text-emerald-300">
689|                      contato@meutrampo.com.br
690|                    </a>
691|                  </div>
692|                </div>
693|              </div>
694|
695|              <div className="bg-slate-900 p-6 rounded-xl border border-emerald-500/20">
696|                <div className="flex items-center gap-4">
697|                  <div className="w-12 h-12 bg-emerald-500/20 rounded-xl flex items-center justify-center">
698|                    <Clock className="h-6 w-6 text-emerald-400" />
699|                  </div>
700|                  <div>
701|                    <h3 className="text-white font-medium">Horário de Atendimento</h3>
702|                    <p className="text-gray-400">Segunda a Sexta: 8h às 18h</p>
703|                    <p className="text-gray-400">Sábado: 9h às 13h</p>
704|                  </div>
705|                </div>
706|              </div>
707|            </div>
708|
709|            {/* Quick WhatsApp CTA */}
710|            <div className="mt-8 bg-gradient-to-r from-green-600 to-green-500 p-6 rounded-xl">
711|              <h3 className="text-white font-semibold text-lg mb-2">Atendimento Rápido via WhatsApp</h3>
712|              <p className="text-green-100 mb-4">Tire suas dúvidas agora mesmo!</p>
713|              <a 
714|                href={`https://wa.me/${PHONE_WHATSAPP}?text=Olá! Vim pelo site Meu Trampo Brasil e gostaria de mais informações.`}
715|                target="_blank"
716|                rel="noopener noreferrer"
717|                className="inline-flex items-center gap-2 bg-white text-green-600 px-6 py-3 rounded-lg font-semibold hover:bg-green-50 transition-colors"
718|                data-testid="contact-whatsapp-btn"
719|              >
720|                <MessageCircle className="h-5 w-5" />
721|                Chamar no WhatsApp
722|              </a>
723|            </div>
724|          </div>
725|
726|          {/* Contact Form */}
727|          <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20">
728|            <h2 className="text-2xl font-semibold text-white mb-6">Envie uma Mensagem</h2>
729|            
730|            <form onSubmit={handleSubmit} className="space-y-4">
731|              <div>
732|                <label className="block text-gray-400 mb-2">Nome Completo</label>
733|                <input
734|                  type="text"
735|                  value={formData.name}
736|                  onChange={(e) => setFormData({...formData, name: e.target.value})}
737|                  className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
738|                  placeholder="Seu nome"
739|                  required
740|                  data-testid="contact-name-input"
741|                />
742|              </div>
743|
744|              <div className="grid md:grid-cols-2 gap-4">
745|                <div>
746|                  <label className="block text-gray-400 mb-2">E-mail</label>
747|                  <input
748|                    type="email"
749|                    value={formData.email}
750|                    onChange={(e) => setFormData({...formData, email: e.target.value})}
751|                    className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
752|                    placeholder="seu@email.com"
753|                    required
754|                    data-testid="contact-email-input"
755|                  />
756|                </div>
757|                <div>
758|                  <label className="block text-gray-400 mb-2">Telefone</label>
759|                  <input
760|                    type="tel"
761|                    value={formData.phone}
762|                    onChange={(e) => setFormData({...formData, phone: e.target.value})}
763|                    className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
764|                    placeholder="(11) 99999-9999"
765|                    data-testid="contact-phone-input"
766|                  />
767|                </div>
768|              </div>
769|
770|              <div>
771|                <label className="block text-gray-400 mb-2">Assunto</label>
772|                <select
773|                  value={formData.subject}
774|                  onChange={(e) => setFormData({...formData, subject: e.target.value})}
775|                  className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-emerald-500"
776|                  required
777|                  data-testid="contact-subject-select"
778|                >
779|                  <option value="">Selecione um assunto</option>
780|                  <option value="duvida">Dúvida sobre vagas</option>
781|                  <option value="empresa">Sou empresa e quero publicar vagas</option>
782|                  <option value="premium">Dúvida sobre planos premium</option>
783|                  <option value="suporte">Suporte técnico</option>
784|                  <option value="outro">Outro assunto</option>
785|                </select>
786|              </div>
787|
788|              <div>
789|                <label className="block text-gray-400 mb-2">Mensagem</label>
790|                <textarea
791|                  value={formData.message}
792|                  onChange={(e) => setFormData({...formData, message: e.target.value})}
793|                  className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500 h-32 resize-none"
794|                  placeholder="Digite sua mensagem..."
795|                  required
796|                  data-testid="contact-message-textarea"
797|                />
798|              </div>
799|
800|              <button
801|                type="submit"
802|                className="w-full bg-emerald-500 hover:bg-emerald-600 text-white py-3 rounded-lg font-semibold transition-colors flex items-center justify-center gap-2"
803|                data-testid="contact-submit-btn"
804|              >
805|                <Send className="h-5 w-5" />
806|                Enviar Mensagem
807|              </button>
808|            </form>
809|
810|            <p className="text-gray-400 text-sm text-center mt-4">
811|              Ou ligue diretamente: <a href={`tel:${PHONE_NUMBER}`} className="text-emerald-400">{PHONE_NUMBER}</a>
812|            </p>
813|          </div>
814|        </div>
815|      </div>
816|    </div>
817|  );
818|};
819|
820|// Register Page
821|const Register = () => {
822|  const [searchParams] = useSearchParams();
823|  const type = searchParams.get('type') || 'candidate';
824|  const [userType, setUserType] = useState(type);
825|
826|  return (
827|    <div className="min-h-screen bg-slate-950 pt-24">
828|      <div className="max-w-2xl mx-auto px-4 py-8">
829|        <div className="text-center mb-8">
830|          <h1 className="text-3xl font-bold text-white mb-2">Criar Conta</h1>
831|          <p className="text-gray-400">Junte-se a milhares de profissionais e empresas</p>
832|        </div>
833|
834|        {/* Type Selector */}
835|        <div className="flex gap-4 mb-8">
836|          <button
837|            onClick={() => setUserType('candidate')}
838|            className={`flex-1 py-4 rounded-xl font-semibold transition-colors flex items-center justify-center gap-2 ${
839|              userType === 'candidate' 
840|                ? 'bg-emerald-500 text-white' 
841|                : 'bg-slate-900 text-gray-400 border border-emerald-500/20'
842|            }`}
843|            data-testid="register-candidate-tab"
844|          >
845|            <User className="h-5 w-5" />
846|            Sou Candidato
847|          </button>
848|          <button
849|            onClick={() => setUserType('company')}
850|            className={`flex-1 py-4 rounded-xl font-semibold transition-colors flex items-center justify-center gap-2 ${
851|              userType === 'company' 
852|                ? 'bg-emerald-500 text-white' 
853|                : 'bg-slate-900 text-gray-400 border border-emerald-500/20'
854|            }`}
855|            data-testid="register-company-tab"
856|          >
857|            <Building2 className="h-5 w-5" />
858|            Sou Empresa
859|          </button>
860|        </div>
861|
862|        {/* Registration Form */}
863|        <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20">
864|          <form className="space-y-4">
865|            {userType === 'candidate' ? (
866|              <>
867|                <div>
868|                  <label className="block text-gray-400 mb-2">Nome Completo</label>
869|                  <input
870|                    type="text"
871|                    className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
872|                    placeholder="Seu nome completo"
873|                    data-testid="register-name-input"
874|                  />
875|                </div>
876|                <div>
877|                  <label className="block text-gray-400 mb-2">CPF</label>
878|                  <input
879|                    type="text"
880|                    className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
881|                    placeholder="000.000.000-00"
882|                    data-testid="register-cpf-input"
883|                  />
884|                </div>
885|              </>
886|            ) : (
887|              <>
888|                <div>
889|                  <label className="block text-gray-400 mb-2">Nome da Empresa</label>
890|                  <input
891|                    type="text"
892|                    className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
893|                    placeholder="Nome da sua empresa"
894|                    data-testid="register-company-name-input"
895|                  />
896|                </div>
897|                <div>
898|                  <label className="block text-gray-400 mb-2">CNPJ</label>
899|                  <input
900|                    type="text"
901|                    className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
902|                    placeholder="00.000.000/0001-00"
903|                    data-testid="register-cnpj-input"
904|                  />
905|                </div>
906|              </>
907|            )}
908|
909|            <div>
910|              <label className="block text-gray-400 mb-2">E-mail</label>
911|              <input
912|                type="email"
913|                className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
914|                placeholder="seu@email.com"
915|                data-testid="register-email-input"
916|              />
917|            </div>
918|
919|            <div>
920|              <label className="block text-gray-400 mb-2">Telefone</label>
921|              <input
922|                type="tel"
923|                className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
924|                placeholder="(11) 99999-9999"
925|                data-testid="register-phone-input"
926|              />
927|            </div>
928|
929|            <div>
930|              <label className="block text-gray-400 mb-2">Senha</label>
931|              <input
932|                type="password"
933|                className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
934|                placeholder="••••••••"
935|                data-testid="register-password-input"
936|              />
937|            </div>
938|
939|            <div>
940|              <label className="block text-gray-400 mb-2">Confirmar Senha</label>
941|              <input
942|                type="password"
943|                className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
944|                placeholder="••••••••"
945|                data-testid="register-confirm-password-input"
946|              />
947|            </div>
948|
949|            <button
950|              type="submit"
951|              className="w-full bg-emerald-500 hover:bg-emerald-600 text-white py-3 rounded-lg font-semibold transition-colors"
952|              data-testid="register-submit-btn"
953|            >
954|              Criar Conta
955|            </button>
956|          </form>
957|
958|          <p className="text-gray-400 text-center mt-6">
959|            Já tem uma conta? <Link to="/login" className="text-emerald-400 hover:text-emerald-300">Entrar</Link>
960|          </p>
961|
962|          <p className="text-gray-400 text-sm text-center mt-4">
963|            Precisa de ajuda? <a href={`tel:${PHONE_NUMBER}`} className="text-emerald-400">{PHONE_NUMBER}</a>
964|          </p>
965|        </div>
966|      </div>
967|    </div>
968|  );
969|};
970|
971|// Login Page
972|const Login = () => {
973|  return (
974|    <div className="min-h-screen bg-slate-950 pt-24">
975|      <div className="max-w-md mx-auto px-4 py-8">
976|        <div className="text-center mb-8">
977|          <h1 className="text-3xl font-bold text-white mb-2">Entrar</h1>
978|          <p className="text-gray-400">Acesse sua conta</p>
979|        </div>
980|
981|        <div className="bg-slate-900 p-8 rounded-2xl border border-emerald-500/20">
982|          <form className="space-y-4">
983|            <div>
984|              <label className="block text-gray-400 mb-2">E-mail</label>
985|              <input
986|                type="email"
987|                className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
988|                placeholder="seu@email.com"
989|                data-testid="login-email-input"
990|              />
991|            </div>
992|
993|            <div>
994|              <label className="block text-gray-400 mb-2">Senha</label>
995|              <input
996|                type="password"
997|                className="w-full bg-slate-800 border border-emerald-500/20 rounded-lg px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-emerald-500"
998|                placeholder="••••••••"
999|                data-testid="login-password-input"
1000|              />
1001|            </div>
1002|
1003|            <div className="flex justify-between items-center">
1004|              <label className="flex items-center gap-2 text-gray-400">
1005|                <input type="checkbox" className="rounded" />
1006|                Lembrar-me
1007|              </label>
1008|              <a href="#" className="text-emerald-400 hover:text-emerald-300 text-sm">Esqueci minha senha</a>
1009|            </div>
1010|
1011|            <button
1012|              type="submit"
1013|              className="w-full bg-emerald-500 hover:bg-emerald-600 text-white py-3 rounded-lg font-semibold transition-colors"
1014|              data-testid="login-submit-btn"
1015|            >
1016|              Entrar
1017|            </button>
1018|          </form>
1019|
1020|          <p className="text-gray-400 text-center mt-6">
1021|            Não tem uma conta? <Link to="/register" className="text-emerald-400 hover:text-emerald-300">Cadastre-se</Link>
1022|          </p>
1023|
1024|          <p className="text-gray-400 text-sm text-center mt-4">
1025|            Precisa de ajuda? <a href={`tel:${PHONE_NUMBER}`} className="text-emerald-400">{PHONE_NUMBER}</a>
1026|          </p>
1027|        </div>
1028|      </div>
1029|    </div>
1030|  );
1031|};
1032|
1033|// Main App
1034|function App() {
1035|  const [isMenuOpen, setIsMenuOpen] = useState(false);
1036|
1037|  return (
1038|    <div className="App">
1039|      <BrowserRouter>
1040|        <Header isMenuOpen={isMenuOpen} setIsMenuOpen={setIsMenuOpen} />
1041|        <Routes>
1042|          <Route path="/" element={<Home />} />
1043|          <Route path="/vagas" element={<Jobs />} />
1044|          <Route path="/empresas" element={<Companies />} />
1045|          <Route path="/contato" element={<Contact />} />
1046|          <Route path="/register" element={<Register />} />
1047|          <Route path="/login" element={<Login />} />
1048|        </Routes>
1049|        <Footer />
1050|        <WhatsAppButton />
1051|      </BrowserRouter>
1052|    </div>
1053|  );
1054|}
1055|
1056|export default App;
1057|

