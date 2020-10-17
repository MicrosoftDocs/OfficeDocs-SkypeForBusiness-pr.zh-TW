---
title: Lync Server 2013：自訂 XSLT 定義檔案
description: Lync Server 2013：自訂 XSLT 定義檔。
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
ms.openlocfilehash: b248b44c9257fa9f30cc99a3773abf71ddbd8651
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553799"
---
# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="fda2a-103">在 Lync Server 2013 中自訂 XSLT 定義檔案</span><span class="sxs-lookup"><span data-stu-id="fda2a-103">Customizing the XSLT definition file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fda2a-104">_**主題上次修改日期：** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="fda2a-104">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="fda2a-105">規範服務會記錄和封存與每個 Lync Server 2013 和 Persistent Chat Server 交談相關的資料，包括參與者：</span><span class="sxs-lookup"><span data-stu-id="fda2a-105">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="fda2a-106">加入 Persistent 聊天室</span><span class="sxs-lookup"><span data-stu-id="fda2a-106">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="fda2a-107">離開聊天室</span><span class="sxs-lookup"><span data-stu-id="fda2a-107">Leaves a chat room</span></span>

  - <span data-ttu-id="fda2a-108">張貼訊息</span><span class="sxs-lookup"><span data-stu-id="fda2a-108">Posts a message</span></span>

  - <span data-ttu-id="fda2a-109">查看聊天記錄</span><span class="sxs-lookup"><span data-stu-id="fda2a-109">Views chat history</span></span>

  - <span data-ttu-id="fda2a-110">上傳檔案</span><span class="sxs-lookup"><span data-stu-id="fda2a-110">Uploads a file</span></span>

  - <span data-ttu-id="fda2a-111">下載檔案</span><span class="sxs-lookup"><span data-stu-id="fda2a-111">Downloads a file</span></span>

<span data-ttu-id="fda2a-p101">資料會以 XML 提供，您可以使用 XSLT 定義檔，將其轉換成最適合您組織的格式。本主題說明規範服務所建立的 XML 檔案。另外也有提供 XSLT 定義及輸出檔範例。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p101">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="fda2a-115">輸出格式</span><span class="sxs-lookup"><span data-stu-id="fda2a-115">Output Format</span></span>

<span data-ttu-id="fda2a-116">規範服務輸出會先依交談 (Conversation 元素) 分類，再依訊息 (Messages 元素) 分類，如下列程式碼範例所示。</span><span class="sxs-lookup"><span data-stu-id="fda2a-116">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

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

<span data-ttu-id="fda2a-p102">Conversation 元素包含四個元素 (Channel、FirstMessage、StartTimeUTC 及 EndTimeUTC)。Channel 元素包含聊天室的統一資源識別項 (URI)，而 FirstMessage 元素會描述 Messages 元素中的第一則訊息。StartTimeUTC 及 EndTimeUTC 元素提供交談的開始和結束時間，如下列程式碼範例所示。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p102">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="fda2a-p103">Message 元素包含兩個元素 (Sender 和 DateTimeUTC) 及三個屬性 (Type、Content 和 ID)。Sender 元素代表傳送訊息的使用者，而 DateTimeUTC 元素代表事件發生的時間，如下列程式碼範例所示。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p103">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="fda2a-122">下表說明郵件屬性類型、內容及識別碼。</span><span class="sxs-lookup"><span data-stu-id="fda2a-122">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="fda2a-123">Messages 元素屬性</span><span class="sxs-lookup"><span data-stu-id="fda2a-123">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fda2a-124">屬性</span><span class="sxs-lookup"><span data-stu-id="fda2a-124">Attribute</span></span></th>
<th><span data-ttu-id="fda2a-125">描述</span><span class="sxs-lookup"><span data-stu-id="fda2a-125">Description</span></span></th>
<th><span data-ttu-id="fda2a-126">選用/必要</span><span class="sxs-lookup"><span data-stu-id="fda2a-126">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-127">類型</span><span class="sxs-lookup"><span data-stu-id="fda2a-127">Type</span></span></p></td>
<td><p><span data-ttu-id="fda2a-p104">指定訊息類型。訊息類型描述在「訊息元素訊息類型」表格中。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p104">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-130">必要</span><span class="sxs-lookup"><span data-stu-id="fda2a-130">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda2a-131">內容</span><span class="sxs-lookup"><span data-stu-id="fda2a-131">Content</span></span></p></td>
<td><p><span data-ttu-id="fda2a-p105">包含訊息內容。Type 為 Join 或 Part 的訊息不使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p105">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-134">選用</span><span class="sxs-lookup"><span data-stu-id="fda2a-134">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-135">ID</span><span class="sxs-lookup"><span data-stu-id="fda2a-135">ID</span></span></p></td>
<td><p><span data-ttu-id="fda2a-p106">指定內容的唯一識別碼。此屬性僅用於 Type 為 Chat 的訊息。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p106">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-138">選用</span><span class="sxs-lookup"><span data-stu-id="fda2a-138">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fda2a-p107">每個 Sender 元素都包含五個屬性：user name、ID、email、internal 和 URI。這些屬性的說明如下表。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p107">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="fda2a-141">Sender 元素屬性</span><span class="sxs-lookup"><span data-stu-id="fda2a-141">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fda2a-142">屬性</span><span class="sxs-lookup"><span data-stu-id="fda2a-142">Attribute</span></span></th>
<th><span data-ttu-id="fda2a-143">描述</span><span class="sxs-lookup"><span data-stu-id="fda2a-143">Description</span></span></th>
<th><span data-ttu-id="fda2a-144">選用/必要</span><span class="sxs-lookup"><span data-stu-id="fda2a-144">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-145">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="fda2a-145">Username</span></span></p></td>
<td><p><span data-ttu-id="fda2a-146">傳送者的名稱。</span><span class="sxs-lookup"><span data-stu-id="fda2a-146">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-147">選用</span><span class="sxs-lookup"><span data-stu-id="fda2a-147">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda2a-148">ID</span><span class="sxs-lookup"><span data-stu-id="fda2a-148">ID</span></span></p></td>
<td><p><span data-ttu-id="fda2a-149">傳送者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="fda2a-149">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-150">必要</span><span class="sxs-lookup"><span data-stu-id="fda2a-150">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-151">電子郵件</span><span class="sxs-lookup"><span data-stu-id="fda2a-151">Email</span></span></p></td>
<td><p><span data-ttu-id="fda2a-152">傳送者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fda2a-152">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-153">選用</span><span class="sxs-lookup"><span data-stu-id="fda2a-153">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda2a-154">內部</span><span class="sxs-lookup"><span data-stu-id="fda2a-154">Internal</span></span></p></td>
<td><p><span data-ttu-id="fda2a-p108">決定使用者為內部使用者或同盟使用者。如果該值設為 true，則為內部使用者。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p108">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-157">選用</span><span class="sxs-lookup"><span data-stu-id="fda2a-157">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-158">Uri</span><span class="sxs-lookup"><span data-stu-id="fda2a-158">Uri</span></span></p></td>
<td><p><span data-ttu-id="fda2a-159">使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="fda2a-159">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="fda2a-160">必要</span><span class="sxs-lookup"><span data-stu-id="fda2a-160">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fda2a-p109">下表說明 Messages 元素可包含的訊息類型。其中也提供各元素的用法範例。</span><span class="sxs-lookup"><span data-stu-id="fda2a-p109">The following table describes the message types that the Messages element can contain. It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="fda2a-163">Message 元素訊息類型</span><span class="sxs-lookup"><span data-stu-id="fda2a-163">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fda2a-164">郵件類型</span><span class="sxs-lookup"><span data-stu-id="fda2a-164">Message Type</span></span></th>
<th><span data-ttu-id="fda2a-165">描述</span><span class="sxs-lookup"><span data-stu-id="fda2a-165">Description</span></span></th>
<th><span data-ttu-id="fda2a-166">程式碼範例</span><span class="sxs-lookup"><span data-stu-id="fda2a-166">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-167">加入</span><span class="sxs-lookup"><span data-stu-id="fda2a-167">Join</span></span></p></td>
<td><p><span data-ttu-id="fda2a-168">使用者加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="fda2a-168">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda2a-169">部分</span><span class="sxs-lookup"><span data-stu-id="fda2a-169">Part</span></span></p></td>
<td><p><span data-ttu-id="fda2a-170">使用者離開聊天室。</span><span class="sxs-lookup"><span data-stu-id="fda2a-170">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-171">聊天</span><span class="sxs-lookup"><span data-stu-id="fda2a-171">Chat</span></span></p></td>
<td><p><span data-ttu-id="fda2a-172">傳送者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fda2a-172">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda2a-173">Backchat</span><span class="sxs-lookup"><span data-stu-id="fda2a-173">Backchat</span></span></p></td>
<td><p><span data-ttu-id="fda2a-174">使用者要求聊天歷程記錄中的內容。</span><span class="sxs-lookup"><span data-stu-id="fda2a-174">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda2a-175">File upload</span><span class="sxs-lookup"><span data-stu-id="fda2a-175">File upload</span></span></p></td>
<td><p><span data-ttu-id="fda2a-176">使用者上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="fda2a-176">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda2a-177">File download</span><span class="sxs-lookup"><span data-stu-id="fda2a-177">File download</span></span></p></td>
<td><p><span data-ttu-id="fda2a-178">使用者下載檔案。</span><span class="sxs-lookup"><span data-stu-id="fda2a-178">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="fda2a-179">預設持續性聊天輸出 XSD 和範例 XSL 轉換</span><span class="sxs-lookup"><span data-stu-id="fda2a-179">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="fda2a-180">下列程式碼範例包含規範伺服器中的預設輸出。</span><span class="sxs-lookup"><span data-stu-id="fda2a-180">The following code sample contains the default output from the Compliance Server.</span></span>

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

<span data-ttu-id="fda2a-181">下列程式碼範例包含 XSL 轉換範例。</span><span class="sxs-lookup"><span data-stu-id="fda2a-181">The following code sample contains a sample XSL transform.</span></span>

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

