import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Moon, Sun, Github, Linkedin, Mail } from "lucide-react";

export default function Portfolio() {
  const [darkMode, setDarkMode] = useState(false);
  
  return (
    <div className={`${darkMode ? "bg-gray-900 text-white" : "bg-white text-black"} min-h-screen p-6 transition-all`}> 
      {/* Navbar */}
      <nav className="flex justify-between items-center py-4">
        <h1 className="text-2xl font-bold">Abhisek Kumar</h1>
        <Button onClick={() => setDarkMode(!darkMode)}>
          {darkMode ? <Sun size={20} /> : <Moon size={20} />}
        </Button>
      </nav>

      {/* Hero Section */}
      <div className="text-center my-10">
        <h2 className="text-4xl font-bold">AI/ML Enthusiast & Full Stack Developer</h2>
        <p className="mt-4 text-lg">Building innovative solutions through Data Science, AI, and Web Technologies</p>
      </div>

      {/* Tech Stack */}
      <div className="flex flex-wrap justify-center gap-4 my-8">
        {['Python', 'TensorFlow', 'LangChain', 'Docker', 'SQL', 'React', 'Node.js'].map((tech) => (
          <span key={tech} className="px-4 py-2 bg-blue-500 text-white rounded-xl">{tech}</span>
        ))}
      </div>

      {/* Projects */}
      <div className="my-10">
        <h3 className="text-3xl font-semibold mb-6">Projects</h3>
        <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
          {[
            { name: "QuestForge", desc: "LLM-powered document retrieval system", link: "#" },
            { name: "Skin Cancer Detection", desc: "Hybrid CNN model using InceptionV3 & DenseNet121", link: "#" }
          ].map((project) => (
            <Card key={project.name} className="p-4 hover:shadow-lg transition">
              <CardContent>
                <h4 className="text-xl font-semibold">{project.name}</h4>
                <p className="mt-2 text-gray-400">{project.desc}</p>
                <a href={project.link} className="mt-3 inline-block text-blue-400">View Project →</a>
              </CardContent>
            </Card>
          ))}
        </div>
      </div>

      {/* Contact */}
      <div className="my-10 text-center">
        <h3 className="text-2xl font-semibold">Let's Connect!</h3>
        <div className="flex justify-center gap-6 mt-4">
          <a href="https://github.com/aveseq" target="_blank" rel="noopener noreferrer"><Github size={30} /></a>
          <a href="https://linkedin.com/in/aveseq" target="_blank" rel="noopener noreferrer"><Linkedin size={30} /></a>
          <a href="mailto:abhishek.kumar2021c@vitstudent.ac.in"><Mail size={30} /></a>
        </div>
      </div>
    </div>
  );
}
