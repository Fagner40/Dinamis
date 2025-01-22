"use client"

import { useState } from "react"
import { Menu, X } from "lucide-react"

export default function DinamisConsultoria() {
  const [isMenuOpen, setIsMenuOpen] = useState(false)
  const [formStatus, setFormStatus] = useState<string | null>(null)

  const toggleMenu = () => setIsMenuOpen(!isMenuOpen)

  const handleSubmit = (e: React.FormEvent<HTMLFormElement>) => {
    e.preventDefault()
    // Here you would typically send the form data to a server
    setFormStatus("Mensagem enviada com sucesso!")
    // Reset form fields here
  }

  return (
    <div className="min-h-screen flex flex-col">
      <header className="bg-gray-800 text-white">
        <div className="container mx-auto px-4 py-6 flex justify-between items-center">
          <div className="logo">
            <h1 className="text-2xl font-bold">Dinamis</h1>
            <p className="text-sm">Consultoria Empresarial e Contábil</p>
          </div>
          <nav className="hidden md:flex space-x-4">
            <a href="#sobre" className="hover:text-gray-300">
              Sobre Nós
            </a>
            <a href="#servicos" className="hover:text-gray-300">
              Serviços
            </a>
            <a href="#equipe" className="hover:text-gray-300">
              Equipe
            </a>
            <a href="#contato" className="hover:text-gray-300">
              Contato
            </a>
          </nav>
          <button className="md:hidden" onClick={toggleMenu}>
            {isMenuOpen ? <X /> : <Menu />}
          </button>
        </div>
        {isMenuOpen && (
          <div className="md:hidden">
            <a href="#sobre" className="block py-2 px-4 text-sm hover:bg-gray-700">
              Sobre Nós
            </a>
            <a href="#servicos" className="block py-2 px-4 text-sm hover:bg-gray-700">
              Serviços
            </a>
            <a href="#equipe" className="block py-2 px-4 text-sm hover:bg-gray-700">
              Equipe
            </a>
            <a href="#contato" className="block py-2 px-4 text-sm hover:bg-gray-700">
              Contato
            </a>
          </div>
        )}
      </header>

      <main className="flex-grow">
        <section id="sobre" className="bg-white py-12">
          <div className="container mx-auto px-4">
            <h2 className="text-3xl font-bold mb-4">Sobre Nós</h2>
            <p className="text-gray-600">
              Na Dinamis, oferecemos soluções contábeis e empresariais sob medida para impulsionar o crescimento do seu
              negócio. Nossa missão é garantir o sucesso financeiro e estratégico dos nossos clientes.
            </p>
          </div>
        </section>

        <section id="servicos" className="bg-gray-100 py-12">
          <div className="container mx-auto px-4">
            <h2 className="text-3xl font-bold mb-4">Nossos Serviços</h2>
            <ul className="list-disc list-inside text-gray-600">
              <li>Gestão Contábil e Fiscal</li>
              <li>Consultoria Empresarial</li>
              <li>Planejamento Tributário</li>
              <li>Controle e Gestão Financeira</li>
              <li>Estratégias de Crescimento Empresarial</li>
            </ul>
          </div>
        </section>

        <section id="equipe" className="bg-white py-12">
          <div className="container mx-auto px-4">
            <h2 className="text-3xl font-bold mb-4">Equipe</h2>
            <p className="text-gray-600">
              Contamos com uma equipe altamente qualificada, composta por especialistas em contabilidade, gestão e
              consultoria empresarial, prontos para oferecer o melhor suporte.
            </p>
          </div>
        </section>

        <section id="contato" className="bg-gray-100 py-12">
          <div className="container mx-auto px-4">
            <h2 className="text-3xl font-bold mb-4">Entre em Contato</h2>
            <p className="mb-2">
              Email:{" "}
              <a "admfagnervieira@gmail.com" className="text-blue-600 hover:underline">
                contato@dinamis.com.br
              </a>
            </p>
            <p className="mb-2">
              Telefone:{" "}
              <a
                href="https://wa.me/5581996708514"
                target="_blank"
                rel="noopener noreferrer"
                className="text-blue-600 hover:underline"
              >
                81-99670-8514
              </a>{" "}
              (WhatsApp)
            </p>
            <p className="mb-4">Endereço: Rua trinta e oito, 07, apt206 - Parque Capibaribe, São Lourenço da Mata-PE, CEP 54720-024</p>
            <form onSubmit={handleSubmit} className="max-w-md">
              <div className="mb-4">
                <label htmlFor="nome" className="block text-gray-700 text-sm font-bold mb-2">
                  Nome:
                </label>
                <input
                  type="text"
                  id="nome"
                  name="nome"
                  required
                  className="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                />
              </div>
              <div className="mb-4">
                <label htmlFor="email" className="block text-gray-700 text-sm font-bold mb-2">
                  Email:
                </label>
                <input
                  type="email"
                  id="email"
                  name="email"
                  required
                  className="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                />
              </div>
              <div className="mb-4">
                <label htmlFor="mensagem" className="block text-gray-700 text-sm font-bold mb-2">
                  Mensagem:
                </label>
                <textarea
                  id="mensagem"
                  name="mensagem"
                  rows={4}
                  required
                  className="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                ></textarea>
              </div>
              <button
                type="submit"
                className="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
              >
                Enviar
              </button>
            </form>
            {formStatus && <p className="mt-4 text-green-600">{formStatus}</p>}
          </div>
        </section>
      </main>

      <footer className="bg-gray-800 text-white py-4">
        <div className="container mx-auto px-4 text-center">
          <p>© 2025 Dinamis Consultoria Empresarial e Contábil. Todos os direitos reservados.</p>
        </div>
      </footer>
    </div>
  )
}
