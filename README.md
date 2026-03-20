# viceroy-resort-website
A luxueious website for a resort.
"use client";
import { motion } from "framer-motion";
import Link from "next/link";

export default function Hero() {
  return (
    <section className="relative h-screen min-h-[600px] overflow-hidden flex items-center justify-center">
      {/* Background image with Ken Burns */}
      <div
        className="absolute inset-0 bg-cover bg-center animate-ken-burns"
        style={{
          backgroundImage:
            "url('https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1800&q=80')",
        }}
      />

      {/* Gradient overlays */}
      <div className="absolute inset-0 bg-gradient-to-b from-forest/70 via-forest/40 to-forest/80" />
      <div className="absolute inset-0 bg-gradient-to-r from-forest/30 to-transparent" />

      {/* Content */}
      <div className="relative z-10 text-center px-6 max-w-5xl mx-auto">
        {/* Eyebrow */}
        <motion.p
          initial={{ opacity: 0, letterSpacing: "0.5em" }}
          animate={{ opacity: 1, letterSpacing: "0.3em" }}
          transition={{ duration: 1.2, delay: 0.3 }}
          className="text-[#C9A84C] uppercase text-xs tracking-[0.3em] mb-6 font-body font-medium"
        >
          Mhaismal · Maharashtra · India
        </motion.p>

        {/* Headline */}
        <motion.h1
          initial={{ opacity: 0, y: 30 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 1, delay: 0.6 }}
          className="font-display text-cream text-balance"
          style={{ fontSize: "clamp(3rem, 8vw, 7rem)", lineHeight: 1.05 }}
        >
          Where the Sahyadris
          <br />
          <em>Breathe in Silence</em>
        </motion.h1>

        {/* Divider */}
        <motion.div
          initial={{ scaleX: 0 }}
          animate={{ scaleX: 1 }}
          transition={{ duration: 0.8, delay: 1.2 }}
          className="w-16 h-px bg-[#C9A84C] mx-auto my-8"
        />

        {/* Subtitle */}
        <motion.p
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ duration: 1, delay: 1.4 }}
          className="text-cream/70 font-body font-light text-lg max-w-xl mx-auto leading-relaxed"
        >
          An intimate hill retreat perched above the clouds — where heritage,
          nature, and quiet luxury converge.
        </motion.p>

        {/* CTAs */}
        <motion.div
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.8, delay: 1.7 }}
          className="mt-10 flex flex-col sm:flex-row gap-4 justify-center"
        >
          <Link
            href="/book"
            className="inline-flex items-center justify-center bg-[#C9A84C] hover:bg-[#E2C97A] text-[#1C2B1A] transition-colors duration-300 px-8 py-3.5 text-xs tracking-widest uppercase font-body font-medium"
          >
            Reserve Your Stay
          </Link>
          <Link
            href="/rooms"
            className="inline-flex items-center justify-center border border-cream/40 hover:border-cream text-cream transition-colors duration-300 px-8 py-3.5 text-xs tracking-widest uppercase font-body font-medium"
          >
            Explore Rooms
          </Link>
        </motion.div>
      </div>

      {/* Scroll indicator */}
      <motion.div
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 2.5, duration: 1 }}
        className="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2"
      >
        <span className="text-cream/40 text-xs tracking-widest uppercase font-body">Scroll</span>
        <motion.div
          animate={{ y: [0, 8, 0] }}
          transition={{ duration: 1.5, repeat: Infinity }}
          className="w-px h-10 bg-gradient-to-b from-[#C9A84C]/60 to-transparent"
        />
      </motion.div>
    </section>
  );
}
