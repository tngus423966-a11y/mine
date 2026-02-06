// script.js

document.addEventListener("DOMContentLoaded", () => {
  /* =========================
     1) 섹션 페이드업 (스크롤 진입 시)
     ========================= */
  const sections = document.querySelectorAll(".section");

  // IntersectionObserver 지원 안 되는 환경 대비
  if ("IntersectionObserver" in window) {
    const io = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) entry.target.classList.add("is-visible");
        });
      },
      { threshold: 0.15 }
    );
    sections.forEach((sec) => io.observe(sec));
  } else {
    // fallback: 그냥 전부 보여주기
    sections.forEach((sec) => sec.classList.add("is-visible"));
  }

  /* =========================
     2) 커스텀 커서 (transform 기반)
     ========================= */
  const cursor = document.querySelector(".cursor");

  // 커서 엘리먼트가 없으면 아래 로직 스킵
  if (cursor) {
    // 초기값(화면 중앙)
    /* =========================
   Custom Cursor (즉각 반응)
   ========================= */
const cursor = document.querySelector(".cursor");

if (cursor) {
  cursor.style.opacity = "0";

  window.addEventListener("mousemove", (e) => {
    // 마우스 중심에 정확히 맞추기 (커서 크기 16px 기준)
    const x = e.clientX - 8;
    const y = e.clientY - 8;

    cursor.style.transform = `translate3d(${x}px, ${y}px, 0)`;
    cursor.style.opacity = "1";
  });

  // hover 효과는 그대로 유지
  const hoverSelector = "a, button, .work-item, .guide-card, .guide-preview";

  document.addEventListener("mouseover", (e) => {
    if (e.target.closest(hoverSelector)) {
      cursor.classList.add("is-hover");
    }
  });

  document.addEventListener("mouseout", (e) => {
    if (e.target.closest(hoverSelector)) {
      cursor.classList.remove("is-hover");
    }
  });

  // 키보드 탭 사용 시 기본 커서 복귀
  window.addEventListener("keydown", (e) => {
    if (e.key === "Tab") {
      document.body.style.cursor = "auto";
      cursor.style.opacity = "0";
    }
  });
}

    // 링크/카드 위에 올리면 커서 커지기
    // ✅ DOM이 나중에 추가되는 요소도 대응하려면 이벤트 위임이 더 안정적
    const hoverSelector = "a, button, .work-item, .guide-card, .guide-preview";

    document.addEventListener("mouseover", (e) => {
      const t = e.target.closest(hoverSelector);
      if (t) cursor.classList.add("is-hover");
    });

    document.addEventListener("mouseout", (e) => {
      const t = e.target.closest(hoverSelector);
      if (t) cursor.classList.remove("is-hover");
    });

    // 탭 이동(키보드) 시엔 기본 커서가 더 편하니까 복구
    window.addEventListener("keydown", (e) => {
      if (e.key === "Tab") {
        document.body.style.cursor = "auto";
        // 커스텀 커서도 숨기고 싶으면 아래 주석 해제
        // cursor.style.opacity = "0";
      }
    });
  }

  /* =========================
     3) Branding Image Auto Slider (3초마다)
     ========================= */
  const brandingImages = document.querySelectorAll(
    ".branding-slider .branding-image"
  );

  // ✅ 이미지가 2장 이상일 때만 슬라이드
  if (brandingImages.length >= 2) {
    let brandingIndex = 0;
    const brandingInterval = 3000;

    // 혹시 active가 하나도 없으면 첫 번째에 강제 부여
    const hasActive = Array.from(brandingImages).some((img) =>
      img.classList.contains("active")
    );
    if (!hasActive) brandingImages[0].classList.add("active");

    setInterval(() => {
      brandingImages[brandingIndex].classList.remove("active");
      brandingIndex = (brandingIndex + 1) % brandingImages.length;
      brandingImages[brandingIndex].classList.add("active");
    }, brandingInterval);
  }
});
