/* ✨ Efek Blinking untuk countdown DONE */
@keyframes blinkDone {
  0%, 100% {
    color: #0d47a1;
    text-shadow: 0 0 0 transparent;
    transform: scale(1);
  }
  50% {
    color: #2e7d32;
    text-shadow: 0 0 20px rgba(76, 175, 80, 0.8), 0 0 40px rgba(76, 175, 80, 0.4);
    transform: scale(1.1);
  }
}

.countdown-done {
  animation: blinkDone 1.5s ease-in-out infinite;
  font-size: 1.8rem !important;
  letter-spacing: 4px;
}
