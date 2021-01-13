---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat Server 的合規性服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 摘要：瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 合規性服務。
ms.openlocfilehash: ee7dbc3ad8e7eedcadcc60850e35b753c5fadb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815063"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="6c925-103">在商務用 Skype Server 2015 中設定 Persistent Chat Server 的合規性服務</span><span class="sxs-lookup"><span data-stu-id="6c925-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="6c925-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 合規性服務。</span><span class="sxs-lookup"><span data-stu-id="6c925-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="6c925-105">持續性聊天規範可讓系統管理員維護持續聊天訊息的封存，以及活動的封存。</span><span class="sxs-lookup"><span data-stu-id="6c925-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="6c925-106">規範服務會記錄和封存與每個 Persistent Chat Server 交談相關的資料，包括參與者：</span><span class="sxs-lookup"><span data-stu-id="6c925-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="6c925-107">加入 Persistent 聊天室</span><span class="sxs-lookup"><span data-stu-id="6c925-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="6c925-108">離開聊天室</span><span class="sxs-lookup"><span data-stu-id="6c925-108">Leaves a chat room</span></span>

- <span data-ttu-id="6c925-109">張貼訊息</span><span class="sxs-lookup"><span data-stu-id="6c925-109">Posts a message</span></span>

- <span data-ttu-id="6c925-110">查看聊天記錄</span><span class="sxs-lookup"><span data-stu-id="6c925-110">Views chat history</span></span>

- <span data-ttu-id="6c925-111">上傳檔案</span><span class="sxs-lookup"><span data-stu-id="6c925-111">Uploads a file</span></span>

- <span data-ttu-id="6c925-112">下載檔案</span><span class="sxs-lookup"><span data-stu-id="6c925-112">Downloads a file</span></span>

<span data-ttu-id="6c925-113">此資訊可視需要從規範 SQL 資料庫中檢索。</span><span class="sxs-lookup"><span data-stu-id="6c925-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="6c925-114">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="6c925-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6c925-115">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="6c925-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="6c925-116">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="6c925-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="6c925-117">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="6c925-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="6c925-118">使用 Windows PowerShell 設定規范服務</span><span class="sxs-lookup"><span data-stu-id="6c925-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="6c925-119">使用拓撲產生器來啟用規範服務之後，您可以使用 **CsPersistenChatComplianceConfiguration** 指令程式來設定服務：</span><span class="sxs-lookup"><span data-stu-id="6c925-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="6c925-120">或</span><span class="sxs-lookup"><span data-stu-id="6c925-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="6c925-121">您可以設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="6c925-121">You can set the following parameters:</span></span>

- <span data-ttu-id="6c925-122">AdapterType-可讓您指定配接器類型。</span><span class="sxs-lookup"><span data-stu-id="6c925-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="6c925-123">配接器是協力廠商的產品，可將規範資料庫中的資料轉換成特定的格式。</span><span class="sxs-lookup"><span data-stu-id="6c925-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="6c925-124">預設值為 XML。</span><span class="sxs-lookup"><span data-stu-id="6c925-124">XML is the default.</span></span>

- <span data-ttu-id="6c925-125">OneChatRoomPerOutputFile-此參數可讓您指定要針對每個聊天室建立不同的報告。</span><span class="sxs-lookup"><span data-stu-id="6c925-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="6c925-126">AddChatRoomDetails-啟用時，此參數會記錄資料庫中每個聊天室的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6c925-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="6c925-127">因為此設定會大幅增加資料庫的大小，所以預設會停用此設定。</span><span class="sxs-lookup"><span data-stu-id="6c925-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="6c925-128">AddUserDetails-啟用時，此參數會記錄資料庫中每個聊天室使用者的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6c925-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="6c925-129">因為此設定會大幅增加資料庫的大小，所以預設會停用此設定。</span><span class="sxs-lookup"><span data-stu-id="6c925-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="6c925-130">Identity-此參數可讓規範設定成為特定集合的範圍，包含全域、網站及服務層級。</span><span class="sxs-lookup"><span data-stu-id="6c925-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="6c925-131">預設值為全域層級。</span><span class="sxs-lookup"><span data-stu-id="6c925-131">The default is the global level.</span></span> 

- <span data-ttu-id="6c925-132">RunInterval-此參數會規定伺服器在建立下一個符合性輸出檔之前的時間長度 (預設值為15分鐘) 。</span><span class="sxs-lookup"><span data-stu-id="6c925-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="6c925-133">使用自訂的規範介面卡</span><span class="sxs-lookup"><span data-stu-id="6c925-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="6c925-134">您可以撰寫自訂介面卡，而不是使用隨 Persistent Chat Server 安裝的 XmlAdapter。</span><span class="sxs-lookup"><span data-stu-id="6c925-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="6c925-135">若要完成此工作，您必須提供包含公用類別 (實作了 **IComplianceAdapter** 介面) 的 .NET Framework 組件。</span><span class="sxs-lookup"><span data-stu-id="6c925-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="6c925-136">您必須將此元件放在 Persistent Chat Server 集區中每一部伺服器的 Persistent Chat Server 安裝資料夾中。</span><span class="sxs-lookup"><span data-stu-id="6c925-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="6c925-137">所有符合此規範的伺服器皆可提供規範資料給您的配接器，但規範伺服器不會提供重複的規範資料給您配接器的多個執行個體。</span><span class="sxs-lookup"><span data-stu-id="6c925-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="6c925-138">該介面是在命名空間的 Compliance.dll 元件中定義的  `Microsoft.Rtc.Internal.Chat.Server.Compliance` 。</span><span class="sxs-lookup"><span data-stu-id="6c925-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="6c925-139">此介面定義了您自訂介面卡必須實作的兩種方法。</span><span class="sxs-lookup"><span data-stu-id="6c925-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="6c925-140">當配接器第一次載入時，Persistent Chat 規範伺服器會呼叫下列方法。</span><span class="sxs-lookup"><span data-stu-id="6c925-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="6c925-141">`AdapterConfig`包含與規範介面卡相關的 Persistent Chat 相容性設定：</span><span class="sxs-lookup"><span data-stu-id="6c925-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="6c925-142">只要有要翻譯的新資料，Persistent Chat 規範伺服器便會以週期性的間隔呼叫下列方法。</span><span class="sxs-lookup"><span data-stu-id="6c925-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="6c925-143">此時間間隔相當於  `RunInterval` Persistent Chat 規範設定中的設定：</span><span class="sxs-lookup"><span data-stu-id="6c925-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="6c925-144">`ConversationCollection`包含上次呼叫此方法時所收集到的交談資訊。</span><span class="sxs-lookup"><span data-stu-id="6c925-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="6c925-145">自訂 XSLT 定義檔案</span><span class="sxs-lookup"><span data-stu-id="6c925-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="6c925-146">規範資料會以 XML 形式傳遞，您可以使用 XSLT 定義檔，將其轉換成最適合組織的格式。</span><span class="sxs-lookup"><span data-stu-id="6c925-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="6c925-147">本主題說明規範服務所建立的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="6c925-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="6c925-148">另外也有提供 XSLT 定義及輸出檔範例。</span><span class="sxs-lookup"><span data-stu-id="6c925-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="6c925-149">輸出格式</span><span class="sxs-lookup"><span data-stu-id="6c925-149">Output format</span></span>

<span data-ttu-id="6c925-150">規範服務輸出會依交談分類 (交談元素) ，然後依 message (message 元素) ，如下列程式碼範例所示：</span><span class="sxs-lookup"><span data-stu-id="6c925-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

<span data-ttu-id="6c925-151">Conversation 元素包含四個元素 (Channel、FirstMessage、StartTimeUTC 及 EndTimeUTC)。</span><span class="sxs-lookup"><span data-stu-id="6c925-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="6c925-152">Channel 元素包含聊天室的統一資源識別項 (URI)，而 FirstMessage 元素會描述 Messages 元素中的第一則訊息。</span><span class="sxs-lookup"><span data-stu-id="6c925-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="6c925-153">StartTimeUTC 和 EndTimeUTC 元素會提供交談的開始時間和結束時間，如下列程式碼範例所示：</span><span class="sxs-lookup"><span data-stu-id="6c925-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="6c925-154">Message 元素包含兩個元素 (Sender 和 DateTimeUTC) 及三個屬性 (Type、Content 和 ID)。</span><span class="sxs-lookup"><span data-stu-id="6c925-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="6c925-155">Sender 元素代表傳送郵件的使用者，而 DateTimeUTC 元素表示事件發生的時間，如下列程式碼範例所示：</span><span class="sxs-lookup"><span data-stu-id="6c925-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="6c925-156">下表說明郵件屬性類型、內容及識別碼。</span><span class="sxs-lookup"><span data-stu-id="6c925-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="6c925-157">**Messages 元素屬性**</span><span class="sxs-lookup"><span data-stu-id="6c925-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="6c925-158">**屬性**</span><span class="sxs-lookup"><span data-stu-id="6c925-158">**Attribute**</span></span>|<span data-ttu-id="6c925-159">**描述**</span><span class="sxs-lookup"><span data-stu-id="6c925-159">**Description**</span></span>|<span data-ttu-id="6c925-160">**選用/必要**</span><span class="sxs-lookup"><span data-stu-id="6c925-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c925-161">類型</span><span class="sxs-lookup"><span data-stu-id="6c925-161">Type</span></span>  <br/> |<span data-ttu-id="6c925-p114">指定訊息類型。訊息類型描述在「訊息元素訊息類型」表格中。</span><span class="sxs-lookup"><span data-stu-id="6c925-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="6c925-164">必要</span><span class="sxs-lookup"><span data-stu-id="6c925-164">Required</span></span>  <br/> |
|<span data-ttu-id="6c925-165">內容</span><span class="sxs-lookup"><span data-stu-id="6c925-165">Content</span></span>  <br/> |<span data-ttu-id="6c925-p115">包含訊息內容。Type 為 Join 或 Part 的訊息不使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="6c925-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="6c925-168">選用</span><span class="sxs-lookup"><span data-stu-id="6c925-168">Optional</span></span>  <br/> |
|<span data-ttu-id="6c925-169">識別碼</span><span class="sxs-lookup"><span data-stu-id="6c925-169">ID</span></span>  <br/> |<span data-ttu-id="6c925-p116">指定內容的唯一識別碼。此屬性僅用於 Type 為 Chat 的訊息。</span><span class="sxs-lookup"><span data-stu-id="6c925-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="6c925-172">選用</span><span class="sxs-lookup"><span data-stu-id="6c925-172">Optional</span></span>  <br/> |

<span data-ttu-id="6c925-p117">每個 Sender 元素都包含五個屬性：user name、ID、email、internal 和 URI。這些屬性的說明如下表。</span><span class="sxs-lookup"><span data-stu-id="6c925-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="6c925-175">**Sender 元素屬性**</span><span class="sxs-lookup"><span data-stu-id="6c925-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="6c925-176">**屬性**</span><span class="sxs-lookup"><span data-stu-id="6c925-176">**Attribute**</span></span>|<span data-ttu-id="6c925-177">**描述**</span><span class="sxs-lookup"><span data-stu-id="6c925-177">**Description**</span></span>|<span data-ttu-id="6c925-178">**選用/必要**</span><span class="sxs-lookup"><span data-stu-id="6c925-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c925-179">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="6c925-179">Username</span></span>  <br/> |<span data-ttu-id="6c925-180">傳送者的名稱。</span><span class="sxs-lookup"><span data-stu-id="6c925-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="6c925-181">選用</span><span class="sxs-lookup"><span data-stu-id="6c925-181">Optional</span></span>  <br/> |
|<span data-ttu-id="6c925-182">識別碼</span><span class="sxs-lookup"><span data-stu-id="6c925-182">ID</span></span>  <br/> |<span data-ttu-id="6c925-183">寄件者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="6c925-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="6c925-184">必要</span><span class="sxs-lookup"><span data-stu-id="6c925-184">Required</span></span>  <br/> |
|<span data-ttu-id="6c925-185">電子郵件</span><span class="sxs-lookup"><span data-stu-id="6c925-185">Email</span></span>  <br/> |<span data-ttu-id="6c925-186">寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6c925-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="6c925-187">選用</span><span class="sxs-lookup"><span data-stu-id="6c925-187">Optional</span></span>  <br/> |
|<span data-ttu-id="6c925-188">內部</span><span class="sxs-lookup"><span data-stu-id="6c925-188">Internal</span></span>  <br/> |<span data-ttu-id="6c925-p118">決定使用者為內部使用者或同盟使用者。如果該值設為 true，則為內部使用者。</span><span class="sxs-lookup"><span data-stu-id="6c925-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="6c925-191">選用</span><span class="sxs-lookup"><span data-stu-id="6c925-191">Optional</span></span>  <br/> |
|<span data-ttu-id="6c925-192">Uri</span><span class="sxs-lookup"><span data-stu-id="6c925-192">Uri</span></span>  <br/> |<span data-ttu-id="6c925-193">使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="6c925-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="6c925-194">必要</span><span class="sxs-lookup"><span data-stu-id="6c925-194">Required</span></span>  <br/> |

<span data-ttu-id="6c925-195">下列範例會顯示 Messages 元素可包含的郵件類型。</span><span class="sxs-lookup"><span data-stu-id="6c925-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="6c925-196">其中也提供各元素的用法範例。</span><span class="sxs-lookup"><span data-stu-id="6c925-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="6c925-197">Join-使用者加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="6c925-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="6c925-198">Part-使用者離開聊天室。</span><span class="sxs-lookup"><span data-stu-id="6c925-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="6c925-199">聊天室-寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6c925-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="6c925-200">Backchat-使用者要求聊天記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="6c925-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="6c925-201">檔上傳-使用者上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="6c925-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="6c925-202">檔案下載-使用者下載檔案。</span><span class="sxs-lookup"><span data-stu-id="6c925-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="6c925-203">預設持續性聊天輸出 XSD 和範例 XSL 轉換</span><span class="sxs-lookup"><span data-stu-id="6c925-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="6c925-204">下列程式碼範例包含規範伺服器的預設輸出：</span><span class="sxs-lookup"><span data-stu-id="6c925-204">The following code sample contains the default output from the Compliance Server:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="6c925-205">下列程式碼範例包含的 XSL 轉換範例：</span><span class="sxs-lookup"><span data-stu-id="6c925-205">The following code sample contains a sample XSL transform:</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
