---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := msgraphsdk.NewPostRequestBody()
post := msgraphsdk.NewPost()
requestBody.SetPost(post)
body := msgraphsdk.NewItemBody()
post.SetBody(body)
contentType := ""
body.SetContentType(&contentType)
content := "content-value"
body.SetContent(&content)
receivedDateTime, err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
post.SetReceivedDateTime(&receivedDateTime)
hasAttachments := true
post.SetHasAttachments(&hasAttachments)
from := msgraphsdk.NewRecipient()
post.SetFrom(from)
emailAddress := msgraphsdk.NewEmailAddress()
from.SetEmailAddress(emailAddress)
name := "name-value"
emailAddress.SetName(&name)
address := "address-value"
emailAddress.SetAddress(&address)
sender := msgraphsdk.NewRecipient()
post.SetSender(sender)
emailAddress := msgraphsdk.NewEmailAddress()
sender.SetEmailAddress(emailAddress)
name := "name-value"
emailAddress.SetName(&name)
address := "address-value"
emailAddress.SetAddress(&address)
conversationThreadId := "conversationThreadId-value"
post.SetConversationThreadId(&conversationThreadId)
post.SetNewParticipants( []Recipient {
	msgraphsdk.NewRecipient(),
	SetAdditionalData(map[string]interface{}{
	}
}
conversationId := "conversationId-value"
post.SetConversationId(&conversationId)
createdDateTime, err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
post.SetCreatedDateTime(&createdDateTime)
lastModifiedDateTime, err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
post.SetLastModifiedDateTime(&lastModifiedDateTime)
changeKey := "changeKey-value"
post.SetChangeKey(&changeKey)
post.SetCategories( []String {
	"categories-value",
}
id := "id-value"
post.SetId(&id)
inReplyTo := msgraphsdk.NewPost()
post.SetInReplyTo(inReplyTo)
post.SetAttachments( []Attachment {
	msgraphsdk.NewAttachment(),
lastModifiedDateTime, err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
	SetLastModifiedDateTime(&lastModifiedDateTime)
name := "name-value"
	SetName(&name)
contentType := "contentType-value"
	SetContentType(&contentType)
size := int32(99)
	SetSize(&size)
isInline := true
	SetIsInline(&isInline)
id := "id-value"
	SetId(&id)
	SetAdditionalData(map[string]interface{}{
		"@odata.type": "#microsoft.graph.fileAttachment",
	}
}
groupId := "group-id"
conversationThreadId := "conversationThread-id"
postId := "post-id"
graphClient.GroupsById(&groupId).ThreadsById(&conversationThreadId).PostsById(&postId).Reply(group-id, conversationThread-id, post-id).Post(requestBody)


```