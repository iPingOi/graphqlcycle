
# Graphql with GOLang using [gqlgen](https://gqlgen.com/)
## Functionalities

- Create category
- Create course
- Find categories
- Find categories with courses
- Find courses
- Find courses with category


## Graphql queries

```Go run server.go
go run cmd/server/server.go
```

```Graphql queries
# Create category #
mutation createCategory {
  createCategory(input: {name: "Tecnologia", description: "Cursos de Tecnologia"}) {
    id
    name
    description
  }
}

# Create course #
mutation createCourse {
  createCourse(input: {name: "Full Cycle", description: "The best!", categoryId: "53ff5e69-79ea-4fd5-bbfc-867e09a89a85"}) {
    id
    name
  }
}

# Find categories #
query queryCategories {
  categories {
    id
    name
    description
  }
}

# Find categories with courses #
query queryCategoriesWithCourses {
  categories {
    id
    name
    description
    courses {
      id
      name
    }
  }
}

# Find courses #
query queryCourses {
  courses {
    id
    name
  }
}

# Find courses with category #
query queryCoursesWithCategory {
  courses {
    id
    name
    description
    category {
      id
      name
      description
    }
  }
}
```

