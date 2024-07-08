## How to use

### [Mill](https://mill-build.com)

```scala
object MyModule extends ScalaModule {
  override def repositoriesTask = T.task {
    super.repositoriesTask() ++ Seq(
      MavenRepository("https://arturaz.github.io/packages/ivy2"),
      MavenRepository("https://arturaz.github.io/packages/maven/repository"),
    )
  }
}
```

### [SBT](https://www.scala-sbt.org)

Read the [SBT documentation](https://www.scala-sbt.org/1.x/docs/Resolvers.html#URL).