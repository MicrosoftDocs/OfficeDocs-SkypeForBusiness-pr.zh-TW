---
title: Lync Server 2013：自訂 XSLT 定義檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing the XSLT definition file
ms:assetid: f18dd78c-3598-4f38-b496-96b750c6e518
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679898(v=OCS.15)
ms:contentKeyID: 49557733
ms.date: 09/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf2ab41ed1d9a57f3a3ad5e55e78f46055fc8e87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="140c4-102">在 Lync Server 2013 中自訂 XSLT 定義檔案</span><span class="sxs-lookup"><span data-stu-id="140c4-102">Customizing the XSLT definition file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="140c4-103">_**主題上次修改日期：** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="140c4-103">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="140c4-104">合規性服務會記錄及歸檔與每個 Lync Server 2013 （持續聊天伺服器交談）相關的資料，包括參與者：</span><span class="sxs-lookup"><span data-stu-id="140c4-104">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="140c4-105">加入持久聊天室</span><span class="sxs-lookup"><span data-stu-id="140c4-105">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="140c4-106">離開聊天室</span><span class="sxs-lookup"><span data-stu-id="140c4-106">Leaves a chat room</span></span>

  - <span data-ttu-id="140c4-107">張貼訊息</span><span class="sxs-lookup"><span data-stu-id="140c4-107">Posts a message</span></span>

  - <span data-ttu-id="140c4-108">查看聊天記錄</span><span class="sxs-lookup"><span data-stu-id="140c4-108">Views chat history</span></span>

  - <span data-ttu-id="140c4-109">上傳檔案</span><span class="sxs-lookup"><span data-stu-id="140c4-109">Uploads a file</span></span>

  - <span data-ttu-id="140c4-110">下載檔案</span><span class="sxs-lookup"><span data-stu-id="140c4-110">Downloads a file</span></span>

<span data-ttu-id="140c4-111">資料會以 XML 形式傳送，您可以使用 XSLT 定義檔，將其轉換成最符合您組織的格式。</span><span class="sxs-lookup"><span data-stu-id="140c4-111">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="140c4-112">本主題描述合規性服務所建立的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="140c4-112">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="140c4-113">它也提供 XSLT 定義和輸出檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="140c4-113">It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="140c4-114">輸出格式</span><span class="sxs-lookup"><span data-stu-id="140c4-114">Output Format</span></span>

<span data-ttu-id="140c4-115">合規性服務輸出是依交談（交談元素），然後依訊息（Messages 元素）來分類，如下列程式碼範例所示。</span><span class="sxs-lookup"><span data-stu-id="140c4-115">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

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

<span data-ttu-id="140c4-116">交談元素包含四個元素（通道、FirstMessage、StartTimeUTC 和 EndTimeUTC）。</span><span class="sxs-lookup"><span data-stu-id="140c4-116">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="140c4-117">通道元素包含聊天室的統一資源識別項（URI），而 FirstMessage 元素則說明 Messages 元素中的第一封郵件。</span><span class="sxs-lookup"><span data-stu-id="140c4-117">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="140c4-118">StartTimeUTC 和 EndTimeUTC 元素會提供交談的開始和結束時間，如下列程式碼範例所示。</span><span class="sxs-lookup"><span data-stu-id="140c4-118">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="140c4-119">Message 元素包含兩個元素（寄件者與 DateTimeUTC）和三個屬性（類型、內容和識別碼）。</span><span class="sxs-lookup"><span data-stu-id="140c4-119">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="140c4-120">Sender 元素代表傳送訊息的使用者，而 DateTimeUTC 元素則代表事件發生的時間，如下列程式碼範例所示。</span><span class="sxs-lookup"><span data-stu-id="140c4-120">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="140c4-121">下表說明訊息屬性類型、內容和識別碼。</span><span class="sxs-lookup"><span data-stu-id="140c4-121">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="140c4-122">郵件元素屬性</span><span class="sxs-lookup"><span data-stu-id="140c4-122">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="140c4-123">Attribute</span><span class="sxs-lookup"><span data-stu-id="140c4-123">Attribute</span></span></th>
<th><span data-ttu-id="140c4-124">說明</span><span class="sxs-lookup"><span data-stu-id="140c4-124">Description</span></span></th>
<th><span data-ttu-id="140c4-125">選擇性/必要</span><span class="sxs-lookup"><span data-stu-id="140c4-125">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="140c4-126">類型</span><span class="sxs-lookup"><span data-stu-id="140c4-126">Type</span></span></p></td>
<td><p><span data-ttu-id="140c4-127">指定郵件類型。</span><span class="sxs-lookup"><span data-stu-id="140c4-127">Specifies the message type.</span></span> <span data-ttu-id="140c4-128">訊息類型將在 [訊息元素] 訊息類型資料表中說明。</span><span class="sxs-lookup"><span data-stu-id="140c4-128">The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="140c4-129">必要</span><span class="sxs-lookup"><span data-stu-id="140c4-129">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="140c4-130">內容</span><span class="sxs-lookup"><span data-stu-id="140c4-130">Content</span></span></p></td>
<td><p><span data-ttu-id="140c4-131">包含郵件的內容。</span><span class="sxs-lookup"><span data-stu-id="140c4-131">Contains the content of the message.</span></span> <span data-ttu-id="140c4-132">含有連線類型或元件的訊息，不會使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="140c4-132">Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="140c4-133">選用</span><span class="sxs-lookup"><span data-stu-id="140c4-133">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="140c4-134">標識號</span><span class="sxs-lookup"><span data-stu-id="140c4-134">ID</span></span></p></td>
<td><p><span data-ttu-id="140c4-135">指定內容的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="140c4-135">Specifies the unique ID of the content.</span></span> <span data-ttu-id="140c4-136">這個屬性只會與聊天類型的訊息搭配使用。</span><span class="sxs-lookup"><span data-stu-id="140c4-136">This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="140c4-137">選用</span><span class="sxs-lookup"><span data-stu-id="140c4-137">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="140c4-138">每個寄件者元素都包含五個屬性：使用者名稱、識別碼、電子郵件、內部和 URI。</span><span class="sxs-lookup"><span data-stu-id="140c4-138">Each Sender element contains five attributes: the user name, ID, email, internal, and URI.</span></span> <span data-ttu-id="140c4-139">下表說明這些屬性。</span><span class="sxs-lookup"><span data-stu-id="140c4-139">These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="140c4-140">寄件者元素屬性</span><span class="sxs-lookup"><span data-stu-id="140c4-140">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="140c4-141">Attribute</span><span class="sxs-lookup"><span data-stu-id="140c4-141">Attribute</span></span></th>
<th><span data-ttu-id="140c4-142">說明</span><span class="sxs-lookup"><span data-stu-id="140c4-142">Description</span></span></th>
<th><span data-ttu-id="140c4-143">選擇性/必要</span><span class="sxs-lookup"><span data-stu-id="140c4-143">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="140c4-144">Username</span><span class="sxs-lookup"><span data-stu-id="140c4-144">Username</span></span></p></td>
<td><p><span data-ttu-id="140c4-145">寄件者的名稱。</span><span class="sxs-lookup"><span data-stu-id="140c4-145">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="140c4-146">選用</span><span class="sxs-lookup"><span data-stu-id="140c4-146">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="140c4-147">標識號</span><span class="sxs-lookup"><span data-stu-id="140c4-147">ID</span></span></p></td>
<td><p><span data-ttu-id="140c4-148">寄件者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="140c4-148">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="140c4-149">必要</span><span class="sxs-lookup"><span data-stu-id="140c4-149">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="140c4-150">電子郵件</span><span class="sxs-lookup"><span data-stu-id="140c4-150">Email</span></span></p></td>
<td><p><span data-ttu-id="140c4-151">寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="140c4-151">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="140c4-152">選用</span><span class="sxs-lookup"><span data-stu-id="140c4-152">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="140c4-153">內部</span><span class="sxs-lookup"><span data-stu-id="140c4-153">Internal</span></span></p></td>
<td><p><span data-ttu-id="140c4-154">判斷使用者是否為內部使用者或同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="140c4-154">Determines whether the user is an internal user or a federated user.</span></span> <span data-ttu-id="140c4-155">如果該值設定為 true，則使用者為 internal。</span><span class="sxs-lookup"><span data-stu-id="140c4-155">If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="140c4-156">選用</span><span class="sxs-lookup"><span data-stu-id="140c4-156">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="140c4-157">Url</span><span class="sxs-lookup"><span data-stu-id="140c4-157">Uri</span></span></p></td>
<td><p><span data-ttu-id="140c4-158">使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="140c4-158">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="140c4-159">必要</span><span class="sxs-lookup"><span data-stu-id="140c4-159">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="140c4-160">下表說明 Messages 元素可包含的郵件類型。</span><span class="sxs-lookup"><span data-stu-id="140c4-160">The following table describes the message types that the Messages element can contain.</span></span> <span data-ttu-id="140c4-161">它也提供如何使用每個元素的範例。</span><span class="sxs-lookup"><span data-stu-id="140c4-161">It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="140c4-162">郵件元素訊息類型</span><span class="sxs-lookup"><span data-stu-id="140c4-162">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="140c4-163">郵件類型</span><span class="sxs-lookup"><span data-stu-id="140c4-163">Message Type</span></span></th>
<th><span data-ttu-id="140c4-164">說明</span><span class="sxs-lookup"><span data-stu-id="140c4-164">Description</span></span></th>
<th><span data-ttu-id="140c4-165">程式碼範例</span><span class="sxs-lookup"><span data-stu-id="140c4-165">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="140c4-166">起來</span><span class="sxs-lookup"><span data-stu-id="140c4-166">Join</span></span></p></td>
<td><p><span data-ttu-id="140c4-167">使用者加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="140c4-167">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="140c4-168">部件</span><span class="sxs-lookup"><span data-stu-id="140c4-168">Part</span></span></p></td>
<td><p><span data-ttu-id="140c4-169">使用者離開聊天室。</span><span class="sxs-lookup"><span data-stu-id="140c4-169">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="140c4-170">聊天</span><span class="sxs-lookup"><span data-stu-id="140c4-170">Chat</span></span></p></td>
<td><p><span data-ttu-id="140c4-171">寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="140c4-171">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="140c4-172">Backchat</span><span class="sxs-lookup"><span data-stu-id="140c4-172">Backchat</span></span></p></td>
<td><p><span data-ttu-id="140c4-173">使用者要求聊天記錄中的內容。</span><span class="sxs-lookup"><span data-stu-id="140c4-173">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="140c4-174">檔案上傳</span><span class="sxs-lookup"><span data-stu-id="140c4-174">File upload</span></span></p></td>
<td><p><span data-ttu-id="140c4-175">使用者上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="140c4-175">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="140c4-176">檔案下載</span><span class="sxs-lookup"><span data-stu-id="140c4-176">File download</span></span></p></td>
<td><p><span data-ttu-id="140c4-177">使用者下載檔案。</span><span class="sxs-lookup"><span data-stu-id="140c4-177">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="140c4-178">預設持續聊天輸出 XSD 和範例 XSL 轉換</span><span class="sxs-lookup"><span data-stu-id="140c4-178">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="140c4-179">下列程式碼範例包含合規性伺服器的預設輸出。</span><span class="sxs-lookup"><span data-stu-id="140c4-179">The following code sample contains the default output from the Compliance Server.</span></span>

    <?xml version="1.0" encoding="utf-8"?>
    <xs:schema id="Conversations"  xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
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

<span data-ttu-id="140c4-180">下列程式碼範例包含範例 XSL 轉換。</span><span class="sxs-lookup"><span data-stu-id="140c4-180">The following code sample contains a sample XSL transform.</span></span>

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

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

