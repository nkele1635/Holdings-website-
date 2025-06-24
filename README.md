import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { BarChart, Bar, XAxis, YAxis, Tooltip, ResponsiveContainer } from "recharts";

const data = [
  { name: 'Q1', revenue: 24000 },
  { name: 'Q2', revenue: 13980 },
  { name: 'Q3', revenue: 9800 },
  { name: 'Q4', revenue: 14800 },
];

export default function Dashboard() {
  return (
    <div className="min-h-screen bg-gray-100 p-6">
      <h1 className="text-3xl font-bold mb-6 text-center">Holdings Company Dashboard</h1>

      <div className="grid gap-6 grid-cols-1 md:grid-cols-2 xl:grid-cols-4 mb-6">
        <Card className="bg-white shadow">
          <CardContent className="p-4">
            <h2 className="text-lg font-semibold">Total Subsidiaries</h2>
            <p className="text-2xl mt-2">4</p>
          </CardContent>
        </Card>

        <Card className="bg-white shadow">
          <CardContent className="p-4">
            <h2 className="text-lg font-semibold">Active Projects</h2>
            <p className="text-2xl mt-2">12</p>
          </CardContent>
        </Card>

        <Card className="bg-white shadow">
          <CardContent className="p-4">
            <h2 className="text-lg font-semibold">Revenue (YTD)</h2>
            <p className="text-2xl mt-2">$95,000</p>
          </CardContent>
        </Card>

        <Card className="bg-white shadow">
          <CardContent className="p-4">
            <h2 className="text-lg font-semibold">Investors</h2>
            <p className="text-2xl mt-2">38</p>
          </CardContent>
        </Card>
      </div>

      <div className="bg-white p-4 shadow rounded">
        <h2 className="text-xl font-semibold mb-4">Quarterly Revenue Overview</h2>
        <ResponsiveContainer width="100%" height={300}>
          <BarChart data={data}>
            <XAxis dataKey="name" />
            <YAxis />
            <Tooltip />
            <Bar dataKey="revenue" fill="#4f46e5" />
          </BarChart>
        </ResponsiveContainer>
      </div>
    </div>
  );
}
