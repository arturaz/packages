## How to use

### [Mill](https://mill-build.com)

```scala
import coursier.ivy.IvyRepository
import coursier.maven.MavenRepository

object MyModule extends ScalaModule {
  override def repositoriesTask = T.task {
    super.repositoriesTask() ++ Seq(
      IvyRepository.parse(
        "https://arturaz.github.io/packages/ivy2/[organization]/[module](_[scalaVersion])/[revision]/[type]s/[artifact](-[classifier]).[ext]"
      ) match {
        case Left(value)  => throw new Exception(value)
        case Right(value) => value
      },
      MavenRepository("https://arturaz.github.io/packages/maven/repository"),
    )
  }
}
```

### [SBT](https://www.scala-sbt.org)

Read the [SBT documentation](https://www.scala-sbt.org/1.x/docs/Resolvers.html#URL).