"use client";
import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Mail, Github, Linkedin, FileText } from "lucide-react";

const blogPosts = [
  { title: "How I built my design system", url: "/blog/design-system" },
  { title: "Deploying a React site with Vercel", url: "/blog/deploy-vercel" },
];

const galleryImages = ["1.jpg", "2.jpg", "3.jpg"];

export default function PersonalWebsite() {
  return (
    <div className="min-h-screen bg-gray-50 dark:bg-gray-900 text-gray-800 dark:text-white p-8">
      <div className="max-w-4xl mx-auto grid gap-8">
        <header className="text-center">
          <h1 className="text-4xl font-bold">John Doe</h1>
          <p className="text-lg mt-2">Web Developer & Designer</p>
        </header>

        <Card><CardContent className="p-6">
          <h2 className="text-2xl font-semibold mb-2">About Me</h2>
          <p>
            I'm a passionate web developer with experience in React, Node.js, and
            responsive design. I love building intuitive and beautiful user interfaces.
          </p>
        </CardContent></Card>

        <Card><CardContent className="p-6">
          <h2 className="text-2xl font-semibold mb-4">Projects</h2>
          <ul className="list-disc list-inside space-y-2">
            <li><strong>Portfolio Website</strong>: A personal portfolio to showcase my projects.</li>
            <li><strong>Task Manager</strong>: A productivity app built with React and Firebase.</li>
            <li><strong>Design System</strong>: A reusable UI library using Tailwind CSS.</li>
          </ul>
        </CardContent></Card>

        <Card><CardContent className="p-6">
          <h2 className="text-2xl font-semibold mb-4">Photo Gallery</h2>
          <div className="grid grid-cols-3 gap-2">
            {galleryImages.map((img, index) => (
              <img key={index} src={`/images/gallery/${img}`} alt={`Gallery ${index + 1}`} className="rounded-lg h-24 object-cover" />
            ))}
          </div>
        </CardContent></Card>

        <Card><CardContent className="p-6">
          <h2 className="text-2xl font-semibold mb-4">Blog</h2>
          <ul className="space-y-2">
            {blogPosts.map((post, index) => (
              <li key={index}>
                <a href={post.url} className="text-blue-500 hover:underline">{post.title}</a>
              </li>
            ))}
          </ul>
        </CardContent></Card>

        <Card><CardContent className="p-6">
          <h2 className="text-2xl font-semibold mb-4">Contact</h2>
          <div className="flex flex-wrap gap-4">
            <Button variant="outline" asChild><a href="mailto:john@example.com"><Mail className="mr-2" /> Email</a></Button>
            <Button variant="outline" asChild><a href="https://github.com/johndoe" target="_blank"><Github className="mr-2" /> GitHub</a></Button>
            <Button variant="outline" asChild><a href="https://linkedin.com/in/johndoe" target="_blank"><Linkedin className="mr-2" /> LinkedIn</a></Button>
            <Button variant="outline" asChild><a href="/resume.pdf" download><FileText className="mr-2" /> Resume</a></Button>
          </div>
        </CardContent></Card>
      </div>
    </div>
  );
}
