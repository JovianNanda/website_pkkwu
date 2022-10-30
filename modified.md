
        const section = document.querySelectorAll("section")
        const navLink = document.querySelectorAll(".nav-item")
        const nav = document.querySelector("#nav")

        function activeMenuOnScroll() {
            let current = '';

            section.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                const pageOffset = pageYOffset + 300;
                console.log();
                if (pageOffset >= sectionTop)
                    current = section.getAttribute('id');
            })

            navLink.forEach(navItem => {
                navItem.classList.remove("active")
                if (navItem.classList.contains(current)) {
                    navItem.classList.add("active")
                }
            })
        }

        function addShadowOnScroll() {

            if (pageYOffset >= 100) {
                nav.classList.add("shadow-md")
                nav.classList.remove("pt-4")
            } else {
                nav.classList.remove("shadow-md")
                nav.classList.add("pt-4")
            }
        }
        addShadowOnScroll
        activeMenuOnScroll
        window.addEventListener("scroll", addShadowOnScroll)
        window.addEventListener("scroll", activeMenuOnScroll)
