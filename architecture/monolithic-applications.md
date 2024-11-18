# Monoliths

### Disclaimer

These notes are about the software architectural pattern. For other uses of monolith, see [here](https://en.wikipedia.org/wiki/Monolith_(disambiguation)).

## What are they?

A monolith, or monolithic application, is a single unified software application, where all components and methods are interconnected and deployed as a single unit.

## Why use them?

- **Simplicity** As everything is contained in one codebase, the application is much easier to install, run, and develop.

- **Performance** Internal computations tend to be faster than external ones, reducing latency.

- **Ease of testing** Integration testing can be done without managing multiple services.

## Why not use them?

- **Scalability** When all the code is interwoven, it can become difficult to manage as it grows. 

- **Deployment** Even small changes require redeploying the entire application.

- **Tight Coupling** Changing one part of the code can have unforeseen consequences in a different part of the code.

## Example

Monoliths are useful when the application is small and self-contained. It is often used to design an MVP (Minimum Viable Product) for this reason.

## How do they compare?

They are the complete opposite of microservices, which are an architecture composed of multiple, independently deployable services. Monoliths tend to be faster for small teams, but nigh impossible to manage for large projects. Microservices enable parallel development, allowing different teams to work on different services simultaneously.


