# Fast-ETL: A simple way to develop and deploy high-performance batch/stream-based applications.
Fast ETL is a query framework aiming to create and deploy high-performance ETLs, using distributed systems like arrow datafusion o fluvio streaming.

## Use Cases

Fast-ETL will be used to process big data without advanced big data or rust knowledge, just using a simple json with a set of steps over our data sources.

## Arquitecture

This is a simple overview of the architecture.

We will have a Schedular that will check the DAG syntax and send it to the launcher.

Then based on the kind of job (Batch or streaming). The launcher starts sending the application to its respective engine data fusion or fluvio respectively.

Once those applications are finished, it will send a notification to the scheduler, and then the schedule will update its indexes or send a notification to someone that requires this.


The whole project will run on Kubernetes.


![Arquitecture](/Architecture.drawio.svg)

## Build

I've forked this from https://github.com/kakkun61/haskell-invokes-rust
But i got some issues on linux, so i decided to fix using stack.

You should move to your rust project and then run.
`cargo build --release`

Once you've compiled your rust code, you should run your application with.
`stack build --exec haskell-invokes-rust`

## Roadmap

- [x] Simple rust haskell connection.
- [ ] Publish json specifications.
- [x] Design and publish basic architecture.
- [ ] Create basic CI/CD pipelines.
- [ ] Validate SQL syntax on rust.
- [ ] Validate SQL semantic on rust.
- [ ] Connect validators written in rust with haskell.
- [ ] Create connector for fluvio (may involves colaborate with the project).
- [ ] Create connector for apache arrow.

## Resources
Original paper: Bachelor's degree thesis project [here](./Proyecto%20de%202021.docx.pdf) written in Spanish.
