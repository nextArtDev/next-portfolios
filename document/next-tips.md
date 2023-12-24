# Next Points

## Image quality and priority

Quality By default its 80 percent we can improve that manually
priority load the image as fast as possible, for main images

```typescript
            <Image
              src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?fit=crop&w=368&h=368&q=100"
              alt="Ricardo portrait"
              width="192"
              height="192"
              // improve default behavior 
              quality="95"
              priority={true}
              className="h-24 w-24 rounded-full object-cover border-[0.35rem] border-white shadow-xl"
            />
```

## Type of array of objects

When we have array of objects we can just take the first one and lets typescript to infer the type and write number for each element of array

```typescript
type ProjectProps = (typeof projectsData)[number]

export default function Project({
  title,
  description,
  tags,
  imageUrl,
}: ProjectProps) {
  //..
}

```