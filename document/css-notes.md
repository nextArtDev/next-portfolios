# CSS notes 

## Z Index just works on 'relative'

We make header relative to use z-index in it
```JS
<header className="z-[999] relative">
```

## How to push all the elements to up or down

by using _mt-auto_ we can push all the footer elements of the card to the bottom of that. (we should set h-full or terminate the height too)

## tailwind even and odd pseudo classes

```typescript
return (
    <motion.div
      ref={ref}
      style={{
        scale: scaleProgess,
        opacity: opacityProgess,
      }}
      className="group mb-3 sm:mb-8 last:mb-0"
    >
    // after defining one of the group as an even or odd, we should add m or p to push other group element to a side. i.e group-even:ml-[18rem]
      <section className="bg-gray-100 max-w-[42rem] border border-black/5 rounded-lg overflow-hidden sm:pr-8 relative sm:h-[20rem] hover:bg-gray-200 transition sm:group-even:pl-8 dark:text-white dark:bg-white/10 dark:hover:bg-white/20">
        <div className="pt-4 pb-7 px-5 sm:pl-10 sm:pr-2 sm:pt-10 sm:max-w-[50%] flex flex-col h-full sm:group-even:ml-[18rem]">
          <h3 className="text-2xl font-semibold">{title}</h3>
          <p className="mt-2 leading-relaxed text-gray-700 dark:text-white/70">
            {description}
          </p>
          <ul className="flex flex-wrap mt-4 gap-2 sm:mt-auto">
            {tags.map((tag, index) => (
              <li
                className="bg-black/[0.7] px-3 py-1 text-[0.7rem] uppercase tracking-wider text-white rounded-full dark:text-white/70"
                key={index}
              >
                {tag}
              </li>
            ))}
          </ul>
        </div>
// Image is always the second child of section, so section element should be even not image itself: group-even:right 
        <Image
          src={imageUrl}
          alt="Project I worked on"
          quality={95}
          className="absolute hidden sm:block top-8 -right-40 w-[28.25rem] rounded-t-lg shadow-2xl
        transition 
        group-hover:scale-[1.04]
        group-hover:-translate-x-3
        group-hover:translate-y-3
        group-hover:-rotate-2

        group-even:group-hover:translate-x-3
        group-even:group-hover:translate-y-3
        group-even:group-hover:rotate-2

        group-even:right-[initial] 
        group-even:-left-40"
        />
      </section>
    </motion.div>
```

## Getting offset for scroll position of a section

we get that by: _scroll-mt-28_

```typescript
    <motion.section
      ref={ref}
      // scroll-mt-28 adding offset to the top, when we scroll
      className="mb-28 max-w-[45rem] text-center leading-8 sm:mb-40 scroll-mt-28"
      initial={{ opacity: 0, y: 100 }}
      whileInView={{ opacity: 1, y: 0 }}
      transition={{ delay: 0.175 }}
      id="about"
    >
```

## smooth scroll

we put it in the html tag in layout

```typescript
 <html lang="en" className="!scroll-smooth">
```
