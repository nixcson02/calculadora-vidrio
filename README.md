import { useState } from "react";

export default function CalculadoraVidrio() {
  const [altura, setAltura] = useState(1.8);
  const [medida, setMedida] = useState(1.17);
  const [base, setBase] = useState(100000);
  const [precioMetroVidrio, setPrecioMetroVidrio] = useState(80000);

  const calcularValor = () => {
    return (medida * precioMetroVidrio * altura + base).toFixed(2);
  };

  return (
    <div className="p-4 border rounded-xl shadow-lg max-w-sm mx-auto">
      <h2 className="text-xl font-bold mb-4">Calculadora de Vidrio</h2>
      <label className="block mb-2">
        Altura:
        <select
          value={altura}
          onChange={(e) => setAltura(parseFloat(e.target.value))}
          className="ml-2 p-2 border rounded"
        >
          <option value={1.8}>1.8m</option>
          <option value={1.9}>1.9m</option>
        </select>
      </label>
      <label className="block mb-2">
        Medida:
        <input
          type="number"
          value={medida}
          onChange={(e) => setMedida(parseFloat(e.target.value))}
          className="ml-2 p-2 border rounded w-full"
          step="0.01"
        />
      </label>
      <label className="block mb-2">
        Base:
        <input
          type="number"
          value={base}
          onChange={(e) => setBase(parseFloat(e.target.value))}
          className="ml-2 p-2 border rounded w-full"
        />
      </label>
      <label className="block mb-2">
        Precio por Metro de Vidrio:
        <input
          type="number"
          value={precioMetroVidrio}
          onChange={(e) => setPrecioMetroVidrio(parseFloat(e.target.value))}
          className="ml-2 p-2 border rounded w-full"
        />
      </label>
      <p className="mt-4 font-semibold">Valor Calculado: ${calcularValor()}</p>
    </div>
  );
}
