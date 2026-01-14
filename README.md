# lucas.h.s.github.io
site curriculo
import React, { useState } from 'react';
import { 
  Mail, 
  Phone, 
  MapPin, 
  Award, 
  BookOpen, 
  Briefcase, 
  Linkedin, 
  Download, 
  CheckCircle,
  ExternalLink,
  Github,
  MessageSquare
} from 'lucide-react';

const App = () => {
  const [activeSection, setActiveSection] = useState('perfil');

  const personalInfo = {
    name: "Lucas Herzog dos Santos",
    title: "Médico • CRM: 23628 ES",
    email: "herzog570@gmail.com",
    phone: "(27) 99502-4499",
    location: "Espírito Santo, Brasil",
    summary: "Médico recém-formado, com sólida formação acadêmica e experiência prática em hospital universitário, emergência e atenção primária. Busco oportunidades que permitam crescimento profissional e aprimoramento técnico, com foco em soluções resolutivas e organização de fluxos assistenciais."
  };

  const experiences = [
    {
      title: "Internato Médico",
      place: "Hospital Universitário Cassiano Antônio Moraes (HUCAM)",
      period: "Vivência em Hospital Universitário",
      description: "Atuação em ambiente de alta complexidade, participando ativamente de rounds multidisciplinares, discussões de casos e procedimentos médicos sob supervisão."
    },
    {
      title: "Internato Médico - Urgência e Emergência",
      place: "Hospital Estadual de Urgência e Emergência (HEUE)",
      period: "Experiência em Pronto-Socorro",
      description: "Atendimento direto a pacientes críticos e politraumatizados, foco em manejo ágil e fluxos de emergência."
    },
    {
      title: "Atenção Primária à Saúde",
      place: "Unidades de Saúde - Prefeitura de Vitória/ES",
      period: "Saúde da Família e Comunidade",
      description: "Acompanhamento longitudinal de pacientes, realização de consultas ambulatoriais, pré-natal e puericultura."
    }
  ];

  const education = [
    {
      degree: "Graduação em Medicina",
      institution: "Universidade Federal do Espírito Santo (UFES)",
      period: "2020 — 2026"
    }
  ];

  const skills = [
    "Perfil resolutivo",
    "Foco em soluções",
    "Liderança",
    "Trabalho em equipe",
    "Gestão de fluxos assistenciais",
    "Domínio de softwares médicos"
  ];

  const certifications = [
    {
      name: "ACLS - Advanced Cardiovascular Life Support",
      issuer: "American Heart Association"
    }
  ];

  const handleWhatsApp = () => {
    window.open(`https://wa.me/5527995024499`, '_blank');
  };

  const handleEmail = () => {
    window.location.href = `mailto:${personalInfo.email}`;
  };

  return (
    <div className="min-h-screen bg-slate-50 font-sans text-slate-900 pb-20 md:pb-0">
      {/* Header / Hero Section */}
      <header className="bg-gradient-to-br from-cyan-700 to-blue-800 text-white py-12 px-6 shadow-lg">
        <div className="max-w-4xl mx-auto flex flex-col items-center text-center">
          <div className="w-24 h-24 bg-white/20 rounded-full flex items-center justify-center mb-4 backdrop-blur-sm border-2 border-white/30">
            <span className="text-3xl font-bold tracking-wider">LH</span>
          </div>
          <h1 className="text-3xl md:text-4xl font-bold mb-2 tracking-tight">{personalInfo.name}</h1>
          <p className="text-cyan-100 text-lg md:text-xl font-medium mb-6">{personalInfo.title}</p>
          
          <div className="flex flex-wrap justify-center gap-4 text-sm">
            <button onClick={handleEmail} className="flex items-center gap-2 bg-white/10 hover:bg-white/20 px-4 py-2 rounded-full transition-all backdrop-blur-md">
              <Mail size={16} /> {personalInfo.email}
            </button>
            <button onClick={handleWhatsApp} className="flex items-center gap-2 bg-white/10 hover:bg-white/20 px-4 py-2 rounded-full transition-all backdrop-blur-md">
              <Phone size={16} /> {personalInfo.phone}
            </button>
            <div className="flex items-center gap-2 bg-white/10 px-4 py-2 rounded-full backdrop-blur-md">
              <MapPin size={16} /> {personalInfo.location}
            </div>
          </div>
        </div>
      </header>

      <main className="max-w-4xl mx-auto px-6 py-10 grid grid-cols-1 md:grid-cols-3 gap-8">
        
        {/* Sidebar for Desktop / Top Content for Mobile */}
        <div className="md:col-span-1 space-y-8">
          <section>
            <h2 className="text-xs font-bold uppercase tracking-widest text-cyan-600 mb-4 flex items-center gap-2">
              <Award size={16} /> Habilidades e Objetivos
            </h2>
            <div className="flex flex-wrap gap-2">
              {skills.map((skill, index) => (
                <span key={index} className="bg-white border border-slate-200 px-3 py-1.5 rounded-lg text-sm text-slate-700 shadow-sm flex items-center gap-2">
                  <div className="w-1.5 h-1.5 rounded-full bg-cyan-500"></div>
                  {skill}
                </span>
              ))}
            </div>
          </section>

          <section>
            <h2 className="text-xs font-bold uppercase tracking-widest text-cyan-600 mb-4 flex items-center gap-2">
              <BookOpen size={16} /> Idiomas
            </h2>
            <div className="bg-white p-4 rounded-xl shadow-sm border border-slate-200">
              <div className="flex justify-between items-center">
                <span className="font-medium text-slate-800">Inglês</span>
                <span className="text-xs bg-cyan-50 text-cyan-700 px-2 py-1 rounded font-semibold uppercase">Proficiente</span>
              </div>
            </div>
          </section>

          <section>
            <h2 className="text-xs font-bold uppercase tracking-widest text-cyan-600 mb-4 flex items-center gap-2">
              <CheckCircle size={16} /> Certificações
            </h2>
            {certifications.map((cert, index) => (
              <div key={index} className="bg-white p-4 rounded-xl shadow-sm border border-slate-200">
                <h3 className="font-bold text-slate-800 text-sm leading-tight mb-1">{cert.name}</h3>
                <p className="text-xs text-slate-500">{cert.issuer}</p>
              </div>
            ))}
          </section>
        </div>

        {/* Main Content Area */}
        <div className="md:col-span-2 space-y-10">
          
          <section>
            <h2 className="text-xl font-bold text-slate-800 mb-4">Perfil Pessoal</h2>
            <p className="text-slate-600 leading-relaxed bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
              {personalInfo.summary}
            </p>
          </section>

          <section>
            <h2 className="text-xl font-bold text-slate-800 mb-6 flex items-center gap-2">
              <Briefcase className="text-cyan-600" /> Experiência Profissional
            </h2>
            <div className="space-y-6">
              {experiences.map((exp, index) => (
                <div key={index} className="relative pl-6 border-l-2 border-cyan-100 hover:border-cyan-400 transition-colors">
                  <div className="absolute w-3 h-3 bg-cyan-500 rounded-full -left-[7px] top-1.5 ring-4 ring-white"></div>
                  <h3 className="text-lg font-bold text-slate-800">{exp.title}</h3>
                  <p className="text-cyan-700 font-semibold text-sm mb-2">{exp.place}</p>
                  <p className="text-slate-500 text-xs font-medium mb-2 uppercase tracking-wide">{exp.period}</p>
                  <p className="text-slate-600 text-sm leading-relaxed">{exp.description}</p>
                </div>
              ))}
            </div>
          </section>

          <section>
            <h2 className="text-xl font-bold text-slate-800 mb-6 flex items-center gap-2">
              <Award className="text-cyan-600" /> Formação Acadêmica
            </h2>
            {education.map((edu, index) => (
              <div key={index} className="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm flex items-start gap-4">
                <div className="bg-cyan-50 p-3 rounded-lg text-cyan-600">
                  <BookOpen size={24} />
                </div>
                <div>
                  <h3 className="text-lg font-bold text-slate-800">{edu.degree}</h3>
                  <p className="text-slate-600 font-medium">{edu.institution}</p>
                  <p className="text-slate-400 text-sm mt-1">{edu.period}</p>
                </div>
              </div>
            ))}
          </section>
        </div>
      </main>

      {/* Footer / Mobile Action Bar */}
      <footer className="fixed bottom-0 left-0 right-0 bg-white/80 backdrop-blur-lg border-t border-slate-200 p-4 md:static md:bg-transparent md:border-none md:pb-12">
        <div className="max-w-4xl mx-auto flex gap-3 md:justify-center">
          <button 
            onClick={handleWhatsApp}
            className="flex-1 md:flex-none flex items-center justify-center gap-2 bg-emerald-500 hover:bg-emerald-600 text-white font-bold py-3 px-6 rounded-xl transition-all shadow-lg shadow-emerald-200"
          >
            <MessageSquare size={20} /> <span className="md:inline">WhatsApp</span>
          </button>
          <button 
            onClick={handleEmail}
            className="flex-1 md:flex-none flex items-center justify-center gap-2 bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-6 rounded-xl transition-all shadow-lg shadow-blue-200"
          >
            <Mail size={20} /> <span className="md:inline">E-mail</span>
          </button>
        </div>
      </footer>
    </div>
  );
};

export default App;
