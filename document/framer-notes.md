## scroll Trigger

```typescript
  const { scrollYProgress } = useScroll({
    target: ref,
    // start: 0:bottom of the viewport - riches the:- 1: top of the target
    // end: 1.33:bottom of the viewport gone 33% - beyonds the project - 1: whole of the project
    offset: ['0 1', '1.33 1'],
  })
  const scaleProgress = useTransform(scrollYProgress, [0, 1], [0.8, 1])
  const opacityProgress = useTransform(scrollYProgress, [0, 1], [0.6, 1])

  return (
    <motion.div
      ref={ref}
      style={{
        scale: scaleProgress,
        opacity: opacityProgress,
      }}
      className="group mb-3 sm:mb-8 last:mb-0"
    >
```