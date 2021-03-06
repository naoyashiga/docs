
<amplify-block-switcher>
<amplify-block name="Java">

```java
private GraphQLRequest<String> getPostAndTodo(String postId, String todoId) {
    String document = "query get($postId: ID!, $todoId: ID!) { "
        + "getPost(id: $postId) { "
            + "id "
            + "title "
            + "rating "
        + "} "
        + "getTodo(id: $todoId) { "
            + "id "
            + "name "
        + "} "
    + "}";
    return new SimpleGraphQLRequest<>(
            document, 
            Collections.singletonMap("id", id), 
            Post.class, 
            new GsonVariablesSerializer());
}
```

</amplify-block>
<amplify-block name="Kotlin">

```kotlin
private fun getPostAndTodo(postId: String, todoId: String): GraphQLRequest<String> {
    val document = ("query get(\$postId: ID!, \$todoId: ID!) { "
            + "getPost(id: \$postId) { "
                + "id "
                + "title "
                + "rating "
            + "} "
            + "getTodo(id: \$todoId) { "
                + "id "
                + "name "
            + "} "
        + "}")

    return SimpleGraphQLRequest(
            document,
            mapOf("postId" to "[POST_ID]", "todoId" to "[TODO_ID]"),
            String::class.java,
            GsonVariablesSerializer())
}
```
</amplify-block>
</amplify-block-switcher>