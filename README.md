import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";

const dishes = [
  {
    title: "Grill Prawn Pomelo Salad",
    description:
      "Juicy grilled prawns paired with refreshing pomelo salad, offering a balance of sweet, tangy, and savory flavors in a tropical bite.",
    image: "/grill prawn pomelo salad.jpg",
  },
  {
    title: "Grilled Jumbo Prawn with Garlic Butter",
    description:
      "Jumbo prawns grilled slowly and basted with aromatic garlic butter, resulting in a tender texture and rich flavor profile.",
    image: "/grille bake jumbo prawn.jpg",
  },
  {
    title: "Jimbaran Grilled Fish",
    description:
      "Balinese-style grilled fish with sambal matah and smoky aroma, bringing an authentic island taste.",
    image: "/jimbaran grilled fish.jpg",
  },
  {
    title: "Homemade Gnocchi",
    description:
      "Handmade gnocchi with a soft, chewy texture, served with a light sauce that highlights natural ingredients.",
    image: "/home made gnoochi.jpg",
  },
  {
    title: "Grilled Prawn with Caponata",
    description:
      "Grilled prawns paired with sweet and sour Sicilian-style caponata, offering a flavorful Mediterranean experience.",
    image: "/grilled prawn with caponata.jpg",
  },
  {
    title: "Roasted Butternut Squash",
    description:
      "Perfectly caramelized roasted butternut squash with naturally sweet, creamy texture.",
    image: "/roasted butter nut squash.jpg",
  },
  {
    title: "Seafood Risotto",
    description:
      "Creamy risotto with fresh seafood like prawns, clams, and squid, enriched with a deep seafood broth.",
    image: "/saefood risotto.jpg",
  },
  {
    title: "Summer Poached Prawn Salad",
    description:
      "Light summer salad with poached prawns, crisp vegetables, and a refreshing citrus dressing.",
    image: "/summer poach prawn salad.jpg",
  },
  {
    title: "Surf and Turf",
    description:
      "Classic pairing of grilled beef steak and prawns, served with a modern touch and signature homemade sauce.",
    image: "/surf n turf.jpg",
  },
  {
    title: "Salmon Gravlax",
    description:
      "Salt- and sugar-cured salmon with dill, presented simply to showcase the fresh flavor and tender texture of the fish.",
    image: "/salmon gravlax.jpg",
  },
];

const cvData = {
  name: "I Putu Adi Suarsana",
  position: "Culinary Professional",
  summary:
    "Accomplished culinary professional with expertise in knife skills, mise en place, and portion sizing. Demonstrates proficiency in food quality control and staff training and development, ensuring high standards in every kitchen environment. Experienced in inventory rotation and restaurant openings, contributing to efficient operations and successful launches. Skilled in scheduling and multitasking, effectively managing time and resources to optimise productivity. Committed to advancing culinary excellence through continuous improvement and innovation.",
  experience: [
    {
      role: "Chef de Partie",
      place: "Hotel XYZ",
      years: "2021 - 2024",
    },
    {
      role: "Commis Chef",
      place: "Restoran ABC",
      years: "2019 - 2021",
    },
  ],
  education: "Diploma in Culinary Arts - Culinary Academy Nusantara",
  contact: {
    email: "suarsana@gmail.com",
    phone: "081234567890",
    location: "Bali, Indonesia",
    linkedin: "https://linkedin.com/in/suarsana"
  },
  cvFile: "/cv_adi_suarsana.pdf"
};

export default function Portfolio() {
  return (
    <div className="grid gap-10 p-4 max-w-5xl mx-auto">
      <section className="grid gap-2">
        <h1 className="text-3xl font-bold">Dish Portfolio</h1>
        <p className="text-muted-foreground">
          A showcase of my culinary creations highlighting flavor, technique, and presentation.
        </p>
      </section>

      <section className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        {dishes.map((dish, index) => (
          <Card key={index} className="rounded-2xl overflow-hidden shadow-md">
            <img
              src={dish.image}
              alt={dish.title}
              className="w-full h-48 object-cover"
            />
            <CardContent className="p-4">
              <h2 className="text-xl font-semibold mb-2">{dish.title}</h2>
              <p className="text-sm text-muted-foreground">{dish.description}</p>
            </CardContent>
          </Card>
        ))}
      </section>

      <section className="grid gap-2">
        <h2 className="text-2xl font-bold mt-10">Curriculum Vitae</h2>
        <div className="bg-white shadow-md rounded-2xl p-6 grid gap-3">
          <h3 className="text-xl font-semibold">{cvData.name}</h3>
          <p className="text-muted-foreground">{cvData.position}</p>
          <p>{cvData.summary}</p>
          <div>
            <h4 className="font-semibold">Experience</h4>
            <ul className="list-disc list-inside">
              {cvData.experience.map((exp, idx) => (
                <li key={idx}>
                  {exp.role}, {exp.place} ({exp.years})
                </li>
              ))}
            </ul>
          </div>
          <div>
            <h4 className="font-semibold">Education</h4>
            <p>{cvData.education}</p>
          </div>
          <div>
            <h4 className="font-semibold">Contact</h4>
            <p>Email: {cvData.contact.email}</p>
            <p>Phone: {cvData.contact.phone}</p>
            <p>Location: {cvData.contact.location}</p>
            <p>LinkedIn: <a className="text-blue-500 underline" href={cvData.contact.linkedin} target="_blank">{cvData.contact.linkedin}</a></p>
          </div>
          <div>
            <Button asChild className="mt-4 w-fit">
              <a href={cvData.cvFile} download>
                Download CV
              </a>
            </Button>
          </div>
        </div>
      </section>
    </div>
  );
}


