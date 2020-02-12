---
title: 設定常設聊天室伺服器的規範服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 摘要：瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器合規性服務。
ms.openlocfilehash: f25df3e85112f91c1286c0be49c428c364acf018
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887842"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="aa08f-103">設定常設聊天室伺服器的規範服務</span><span class="sxs-lookup"><span data-stu-id="aa08f-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="aa08f-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器合規性服務。</span><span class="sxs-lookup"><span data-stu-id="aa08f-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="aa08f-105">持續聊天合規性可讓系統管理員維持持久聊天訊息及活動的封存。</span><span class="sxs-lookup"><span data-stu-id="aa08f-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="aa08f-106">合規性服務會記錄及歸檔與每個持續聊天伺服器交談相關的資料，包括參與者：</span><span class="sxs-lookup"><span data-stu-id="aa08f-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="aa08f-107">加入持久聊天室</span><span class="sxs-lookup"><span data-stu-id="aa08f-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="aa08f-108">離開聊天室</span><span class="sxs-lookup"><span data-stu-id="aa08f-108">Leaves a chat room</span></span>

- <span data-ttu-id="aa08f-109">張貼訊息</span><span class="sxs-lookup"><span data-stu-id="aa08f-109">Posts a message</span></span>

- <span data-ttu-id="aa08f-110">查看聊天記錄</span><span class="sxs-lookup"><span data-stu-id="aa08f-110">Views chat history</span></span>

- <span data-ttu-id="aa08f-111">上傳檔案</span><span class="sxs-lookup"><span data-stu-id="aa08f-111">Uploads a file</span></span>

- <span data-ttu-id="aa08f-112">下載檔案</span><span class="sxs-lookup"><span data-stu-id="aa08f-112">Downloads a file</span></span>

<span data-ttu-id="aa08f-113">您可以視需要從合規性 SQL 資料庫中檢索此資訊。</span><span class="sxs-lookup"><span data-stu-id="aa08f-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="aa08f-114">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="aa08f-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aa08f-115">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="aa08f-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="aa08f-116">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="aa08f-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="aa08f-117">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="aa08f-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="aa08f-118">使用 Windows PowerShell 設定合規性服務</span><span class="sxs-lookup"><span data-stu-id="aa08f-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="aa08f-119">使用 [拓撲結構建立器] 啟用合規性服務之後，您可以使用**CsPersistenChatComplianceConfiguration** Cmdlet 來設定服務：</span><span class="sxs-lookup"><span data-stu-id="aa08f-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="aa08f-120">或</span><span class="sxs-lookup"><span data-stu-id="aa08f-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="aa08f-121">您可以設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="aa08f-121">You can set the following parameters:</span></span>

- <span data-ttu-id="aa08f-122">AdapterType-可讓您指定配接器類型。</span><span class="sxs-lookup"><span data-stu-id="aa08f-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="aa08f-123">配接器是協力廠商的產品，可將合規性資料庫中的資料轉換成特定的格式。</span><span class="sxs-lookup"><span data-stu-id="aa08f-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="aa08f-124">[XML] 是預設值。</span><span class="sxs-lookup"><span data-stu-id="aa08f-124">XML is the default.</span></span>

- <span data-ttu-id="aa08f-125">OneChatRoomPerOutputFile-此參數可讓您指定要為每個聊天室建立不同的報表。</span><span class="sxs-lookup"><span data-stu-id="aa08f-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="aa08f-126">AddChatRoomDetails-啟用時，此參數會記錄資料庫中每個聊天室的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="aa08f-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="aa08f-127">因為此設定會大幅增加資料庫大小，所以預設為停用。</span><span class="sxs-lookup"><span data-stu-id="aa08f-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="aa08f-128">AddUserDetails-啟用時，此參數會記錄資料庫中每個聊天室使用者的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="aa08f-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="aa08f-129">因為此設定會大幅增加資料庫大小，所以預設為停用。</span><span class="sxs-lookup"><span data-stu-id="aa08f-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="aa08f-130">身分識別-此參數可讓規範設定成為特定集合的範圍，包括全域、網站和服務層級。</span><span class="sxs-lookup"><span data-stu-id="aa08f-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="aa08f-131">預設為 [全域] 層級。</span><span class="sxs-lookup"><span data-stu-id="aa08f-131">The default is the global level.</span></span> 

- <span data-ttu-id="aa08f-132">RunInterval-此參數規定伺服器在建立下一個相容性輸出檔案之前的時間長度（預設值為15分鐘）。</span><span class="sxs-lookup"><span data-stu-id="aa08f-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="aa08f-133">使用自訂的合規性配接器</span><span class="sxs-lookup"><span data-stu-id="aa08f-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="aa08f-134">您可以撰寫自訂配接器，而不是使用隨持續聊天伺服器一起安裝的 XmlAdapter。</span><span class="sxs-lookup"><span data-stu-id="aa08f-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="aa08f-135">若要完成這項作業，您必須提供包含實現**IComplianceAdapter**介面之公用類別的 .net Framework 元件。</span><span class="sxs-lookup"><span data-stu-id="aa08f-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="aa08f-136">您必須將此元件放在持續聊天伺服器池中每個伺服器的 [永久聊天伺服器安裝] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="aa08f-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="aa08f-137">任何一個合規性伺服器都可以為您的配接器提供合規性資料，但合規性伺服器將不會提供重複的合規性資料給您的配接器的多個實例。</span><span class="sxs-lookup"><span data-stu-id="aa08f-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="aa08f-138">介面是在命名空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`的合規性 .dll 程式集中定義。</span><span class="sxs-lookup"><span data-stu-id="aa08f-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="aa08f-139">介面定義您的自訂配接器必須實現的兩種方法。</span><span class="sxs-lookup"><span data-stu-id="aa08f-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="aa08f-140">當配接器第一次載入時，Persistent 聊天相容性伺服器將呼叫下列方法。</span><span class="sxs-lookup"><span data-stu-id="aa08f-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="aa08f-141">`AdapterConfig`包含與合規性配接器相關的持續聊天相容性設定：</span><span class="sxs-lookup"><span data-stu-id="aa08f-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="aa08f-142">只要有要翻譯的新資料，持續性聊天規範伺服器就會以週期性的時間間隔呼叫下列方法。</span><span class="sxs-lookup"><span data-stu-id="aa08f-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="aa08f-143">這個時間間隔與持續聊天相容`RunInterval`性設定中的設定相同：</span><span class="sxs-lookup"><span data-stu-id="aa08f-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="aa08f-144">`ConversationCollection`包含上次呼叫此方法時所收集的交談資訊。</span><span class="sxs-lookup"><span data-stu-id="aa08f-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="aa08f-145">自訂 XSLT 定義檔</span><span class="sxs-lookup"><span data-stu-id="aa08f-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="aa08f-146">合規性資料會以 XML 形式傳送，您可以使用 XSLT 定義檔，將其轉換成最符合貴組織的格式。</span><span class="sxs-lookup"><span data-stu-id="aa08f-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="aa08f-147">本主題描述合規性服務所建立的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="aa08f-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="aa08f-148">它也提供 XSLT 定義和輸出檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="aa08f-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="aa08f-149">輸出格式</span><span class="sxs-lookup"><span data-stu-id="aa08f-149">Output format</span></span>

<span data-ttu-id="aa08f-150">合規性服務輸出是依交談（交談元素），然後依訊息（Messages 元素）來分類，如下列程式碼範例所示：</span><span class="sxs-lookup"><span data-stu-id="aa08f-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

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

<span data-ttu-id="aa08f-151">交談元素包含四個元素（通道、FirstMessage、StartTimeUTC 和 EndTimeUTC）。</span><span class="sxs-lookup"><span data-stu-id="aa08f-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="aa08f-152">通道元素包含聊天室的統一資源識別項（URI），而 FirstMessage 元素則說明 Messages 元素中的第一封郵件。</span><span class="sxs-lookup"><span data-stu-id="aa08f-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="aa08f-153">StartTimeUTC 和 EndTimeUTC 元素會提供交談的開始和結束時間，如下列程式碼範例所示：</span><span class="sxs-lookup"><span data-stu-id="aa08f-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="aa08f-154">Message 元素包含兩個元素（寄件者與 DateTimeUTC）和三個屬性（類型、內容和識別碼）。</span><span class="sxs-lookup"><span data-stu-id="aa08f-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="aa08f-155">Sender 元素代表傳送訊息的使用者，而 DateTimeUTC 元素則代表事件發生的時間，如下列程式碼範例所示：</span><span class="sxs-lookup"><span data-stu-id="aa08f-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="aa08f-156">下表說明訊息屬性類型、內容和識別碼。</span><span class="sxs-lookup"><span data-stu-id="aa08f-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="aa08f-157">**郵件元素屬性**</span><span class="sxs-lookup"><span data-stu-id="aa08f-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="aa08f-158">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="aa08f-158">**Attribute**</span></span>|<span data-ttu-id="aa08f-159">**描述**</span><span class="sxs-lookup"><span data-stu-id="aa08f-159">**Description**</span></span>|<span data-ttu-id="aa08f-160">**選擇性/必要**</span><span class="sxs-lookup"><span data-stu-id="aa08f-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa08f-161">類型</span><span class="sxs-lookup"><span data-stu-id="aa08f-161">Type</span></span>  <br/> |<span data-ttu-id="aa08f-162">指定郵件類型。</span><span class="sxs-lookup"><span data-stu-id="aa08f-162">Specifies the message type.</span></span> <span data-ttu-id="aa08f-163">訊息類型將在 [訊息元素] 訊息類型資料表中說明。</span><span class="sxs-lookup"><span data-stu-id="aa08f-163">The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="aa08f-164">必要</span><span class="sxs-lookup"><span data-stu-id="aa08f-164">Required</span></span>  <br/> |
|<span data-ttu-id="aa08f-165">內容</span><span class="sxs-lookup"><span data-stu-id="aa08f-165">Content</span></span>  <br/> |<span data-ttu-id="aa08f-166">包含郵件的內容。</span><span class="sxs-lookup"><span data-stu-id="aa08f-166">Contains the content of the message.</span></span> <span data-ttu-id="aa08f-167">含有連線類型或元件的訊息，不會使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="aa08f-167">Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="aa08f-168">選用</span><span class="sxs-lookup"><span data-stu-id="aa08f-168">Optional</span></span>  <br/> |
|<span data-ttu-id="aa08f-169">標識號</span><span class="sxs-lookup"><span data-stu-id="aa08f-169">ID</span></span>  <br/> |<span data-ttu-id="aa08f-170">指定內容的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="aa08f-170">Specifies the unique ID of the content.</span></span> <span data-ttu-id="aa08f-171">這個屬性只會與聊天類型的訊息搭配使用。</span><span class="sxs-lookup"><span data-stu-id="aa08f-171">This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="aa08f-172">選用</span><span class="sxs-lookup"><span data-stu-id="aa08f-172">Optional</span></span>  <br/> |

<span data-ttu-id="aa08f-173">每個寄件者元素都包含五個屬性：使用者名稱、識別碼、電子郵件、內部和 URI。</span><span class="sxs-lookup"><span data-stu-id="aa08f-173">Each Sender element contains five attributes: the user name, ID, email, internal, and URI.</span></span> <span data-ttu-id="aa08f-174">下表說明這些屬性。</span><span class="sxs-lookup"><span data-stu-id="aa08f-174">These attributes are described in the following table.</span></span>

<span data-ttu-id="aa08f-175">**寄件者元素屬性**</span><span class="sxs-lookup"><span data-stu-id="aa08f-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="aa08f-176">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="aa08f-176">**Attribute**</span></span>|<span data-ttu-id="aa08f-177">**描述**</span><span class="sxs-lookup"><span data-stu-id="aa08f-177">**Description**</span></span>|<span data-ttu-id="aa08f-178">**選擇性/必要**</span><span class="sxs-lookup"><span data-stu-id="aa08f-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa08f-179">Username</span><span class="sxs-lookup"><span data-stu-id="aa08f-179">Username</span></span>  <br/> |<span data-ttu-id="aa08f-180">寄件者的名稱。</span><span class="sxs-lookup"><span data-stu-id="aa08f-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="aa08f-181">選用</span><span class="sxs-lookup"><span data-stu-id="aa08f-181">Optional</span></span>  <br/> |
|<span data-ttu-id="aa08f-182">標識號</span><span class="sxs-lookup"><span data-stu-id="aa08f-182">ID</span></span>  <br/> |<span data-ttu-id="aa08f-183">寄件者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="aa08f-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="aa08f-184">必要</span><span class="sxs-lookup"><span data-stu-id="aa08f-184">Required</span></span>  <br/> |
|<span data-ttu-id="aa08f-185">電子郵件</span><span class="sxs-lookup"><span data-stu-id="aa08f-185">Email</span></span>  <br/> |<span data-ttu-id="aa08f-186">寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="aa08f-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="aa08f-187">選用</span><span class="sxs-lookup"><span data-stu-id="aa08f-187">Optional</span></span>  <br/> |
|<span data-ttu-id="aa08f-188">內部</span><span class="sxs-lookup"><span data-stu-id="aa08f-188">Internal</span></span>  <br/> |<span data-ttu-id="aa08f-189">判斷使用者是否為內部使用者或同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="aa08f-189">Determines whether the user is an internal user or a federated user.</span></span> <span data-ttu-id="aa08f-190">如果該值設定為 true，則使用者為 internal。</span><span class="sxs-lookup"><span data-stu-id="aa08f-190">If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="aa08f-191">選用</span><span class="sxs-lookup"><span data-stu-id="aa08f-191">Optional</span></span>  <br/> |
|<span data-ttu-id="aa08f-192">Url</span><span class="sxs-lookup"><span data-stu-id="aa08f-192">Uri</span></span>  <br/> |<span data-ttu-id="aa08f-193">使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="aa08f-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="aa08f-194">必要</span><span class="sxs-lookup"><span data-stu-id="aa08f-194">Required</span></span>  <br/> |

<span data-ttu-id="aa08f-195">下列範例顯示了 Messages 元素可以包含的郵件類型。</span><span class="sxs-lookup"><span data-stu-id="aa08f-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="aa08f-196">它也提供如何使用每個元素的範例。</span><span class="sxs-lookup"><span data-stu-id="aa08f-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="aa08f-197">[加入]-使用者加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="aa08f-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="aa08f-198">部分-使用者離開聊天室。</span><span class="sxs-lookup"><span data-stu-id="aa08f-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="aa08f-199">聊天-寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="aa08f-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="aa08f-200">Backchat-使用者要求聊天記錄中的內容。</span><span class="sxs-lookup"><span data-stu-id="aa08f-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="aa08f-201">檔案上傳-使用者上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="aa08f-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="aa08f-202">檔案下載-使用者下載檔案。</span><span class="sxs-lookup"><span data-stu-id="aa08f-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="aa08f-203">預設持續聊天輸出 XSD 和範例 XSL 轉換</span><span class="sxs-lookup"><span data-stu-id="aa08f-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="aa08f-204">下列程式碼範例包含合規性伺服器的預設輸出：</span><span class="sxs-lookup"><span data-stu-id="aa08f-204">The following code sample contains the default output from the Compliance Server:</span></span>

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

<span data-ttu-id="aa08f-205">下列程式碼範例包含範例 XSL 轉換：</span><span class="sxs-lookup"><span data-stu-id="aa08f-205">The following code sample contains a sample XSL transform:</span></span>

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
