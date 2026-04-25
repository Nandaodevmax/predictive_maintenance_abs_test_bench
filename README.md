# predictive_maintenance_abs_test_bench
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "e1a1d9e8-fc39-49ef-9022-d06f7f786aeb",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Projeto Fernando - Cientista de Dados Industrial\n"
     ]
    }
   ],
   "source": [
    "print(\"Projeto Fernando - Cientista de Dados Industrial\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "23935ab7-a16c-4c6f-92ca-b7e8fa4ad767",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "['rolamentos', 'desalinhamentos', 'falta de lubrificação', 'sensor com defeito']\n"
     ]
    }
   ],
   "source": [
    "falhas = [\"rolamentos\", \"desalinhamentos\", \"falta de lubrificação\", \"sensor com defeito\"]\n",
    "print(falhas)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "id": "805dfbfd-66d2-4271-b848-1303789438df",
   "metadata": {},
   "outputs": [
    {
     "ename": "NameError",
     "evalue": "name 'df' is not defined",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mNameError\u001b[0m                                 Traceback (most recent call last)",
      "Input \u001b[0;32mIn [4]\u001b[0m, in \u001b[0;36m<cell line: 1>\u001b[0;34m()\u001b[0m\n\u001b[0;32m----> 1\u001b[0m \u001b[43mdf\u001b[49m[\u001b[38;5;124m\"\u001b[39m\u001b[38;5;124mtempo_parado_horas\u001b[39m\u001b[38;5;124m\"\u001b[39m]\u001b[38;5;241m.\u001b[39mmean()\n",
      "\u001b[0;31mNameError\u001b[0m: name 'df' is not defined"
     ]
    }
   ],
   "source": [
    "df[\"tempo_parado_horas\"].mean()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "d42b67fb-3e20-40d8-a524-da504b9c379f",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>data</th>\n",
       "      <th>Equipamento</th>\n",
       "      <th>falha</th>\n",
       "      <th>tempo_parado_horas</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>2026-04-10</td>\n",
       "      <td>Esteira 1</td>\n",
       "      <td>rolamento</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2026-04-11</td>\n",
       "      <td>Esteira 2</td>\n",
       "      <td>desalinhamento</td>\n",
       "      <td>3.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>2026-04-11</td>\n",
       "      <td>Elevador</td>\n",
       "      <td>Sensor</td>\n",
       "      <td>1.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>2026-04-12</td>\n",
       "      <td>Esteira 1</td>\n",
       "      <td>lubrificação</td>\n",
       "      <td>4.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "         data Equipamento           falha  tempo_parado_horas\n",
       "0  2026-04-10   Esteira 1       rolamento                 2.0\n",
       "1  2026-04-11   Esteira 2  desalinhamento                 3.5\n",
       "2  2026-04-11    Elevador          Sensor                 1.0\n",
       "3  2026-04-12   Esteira 1    lubrificação                 4.0"
      ]
     },
     "execution_count": 5,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "dados = { \n",
    "   \"data\": [\"2026-04-10\", \"2026-04-11\", \"2026-04-11\", \"2026-04-12\"],\n",
    "   \"Equipamento\": [\"Esteira 1\", \"Esteira 2\", \"Elevador\", \"Esteira 1\"],\n",
    "   \"falha\": [\"rolamento\", \"desalinhamento\", \"Sensor\", \"lubrificação\"],\n",
    "   \"tempo_parado_horas\": [2, 3.5, 1, 4]\n",
    " }\n",
    "df = pd.DataFrame(dados)\n",
    "df"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "8d6a3f17-feac-4b43-b254-21f356ecfdb5",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Equipamento\n",
       "Elevador     1.0\n",
       "Esteira 1    6.0\n",
       "Esteira 2    3.5\n",
       "Name: tempo_parado_horas, dtype: float64"
      ]
     },
     "execution_count": 6,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.groupby(\"Equipamento\")[\"tempo_parado_horas\"].sum()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "fb4b9efa-6385-4c94-92b4-473b8f95a0d7",
   "metadata": {},
   "outputs": [],
   "source": [
    "df[\"falha\"].value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "17e4569f-44c9-4134-b8ae-1958baf0250c",
   "metadata": {},
   "outputs": [],
   "source": [
    "import matplotlib.pyplot as plt\n",
    "df.groupby(\"Equipamento\")[\"tempo_parado_horas\"].sum().plot(kind=\"bar\")\n",
    "plt.title(\"Tempo de Parada por Equipamento\")\n",
    "plt.xlabel(\"Equipamento\")\n",
    "plt.ylabel(\"Horas Paradas\")\n",
    "\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "2e255d3f-47b7-4dc6-97b5-0f5850e5a8d9",
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd\n",
    "dados = {\n",
    "    \"temperatura\": [70, 85, 90, 60, 95, 80, 100],\n",
    "    \"vibração\": [\"baixa\", \"média\", \"alta\", \"baixa\", \"média\", \"alta\", \"baixa\"],\n",
    "    \"falhou\": [0, 1, 1, 0, 1, 0, 1]\n",
    "}\n",
    "df = pd.DataFrame(dados)\n",
    "df\n",
    "    "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "41136131-3658-4397-a194-2d51e029f4dc",
   "metadata": {},
   "outputs": [],
   "source": [
    "df[\"vibracao\"] = df[\"vibracao\"].map({\n",
    "   \"baixa\": 0,\n",
    "   \"media\": 1,\n",
    "   \"alta\" : 2  \n",
    "})\n",
    "df"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "2c536f92-335c-4875-a6a0-27aa4995d41a",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "anaconda-2022.05-py39",
   "language": "python",
   "name": "conda-env-anaconda-2022.05-py39-py"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.9.12"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
