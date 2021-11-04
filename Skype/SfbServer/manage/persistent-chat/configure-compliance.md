---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat Server 的規範服務
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 摘要：瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 合規性服務。
ms.openlocfilehash: af574e4b449211f1631c332e7f494fba6c75e750
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778313"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中設定 Persistent Chat Server 的規範服務

**摘要：** 瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 合規性服務。

持續性聊天規範可讓系統管理員維護持續聊天訊息的封存，以及活動的封存。 規範服務會記錄和封存與每個 Persistent Chat Server 交談相關的資料，包括參與者：

- 加入 Persistent 聊天室

- 離開聊天室

- 張貼訊息

- 查看聊天記錄

- 上傳檔案

- 下載檔案

您可以視需要從規範 SQL 資料庫中找回此資訊。 

> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>使用 Windows PowerShell 設定規范服務

使用拓撲產生器來啟用規範服務之後，您可以使用 **CsPersistenChatComplianceConfiguration** 指令程式來設定服務：

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

或

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

您可以設定下列參數：

- AdapterType-可讓您指定配接器類型。 配接器是協力廠商的產品，可將規範資料庫中的資料轉換成特定的格式。 預設值為 XML。

- OneChatRoomPerOutputFile-此參數可讓您指定要針對每個聊天室建立不同的報告。

- AddChatRoomDetails-啟用時，此參數會記錄資料庫中每個聊天室的其他詳細資料。 因為此設定會大幅增加資料庫的大小，所以預設會停用此設定。

- AddUserDetails-啟用時，此參數會記錄資料庫中每個聊天室使用者的其他詳細資料。 因為此設定會大幅增加資料庫的大小，所以預設會停用此設定。

- Identity-此參數可讓規範設定成為特定集合的範圍，包含全域、網站及服務層級。 預設值為全域層級。 

- RunInterval-此參數會規定伺服器在建立下一個符合性輸出檔之前的時間長度 (預設值為15分鐘) 。

## <a name="use-a-customized-compliance-adapter"></a>使用自訂的規範介面卡

您可以撰寫自訂介面卡，而不是使用隨 Persistent Chat Server 安裝的 XmlAdapter。 若要完成此工作，您必須提供包含公用類別 (實作了 **IComplianceAdapter** 介面) 的 .NET Framework 組件。 您必須將此元件放在 Persistent Chat Server 集區中每一部伺服器的 Persistent Chat Server 安裝資料夾中。 所有符合此規範的伺服器皆可提供規範資料給您的配接器，但規範伺服器不會提供重複的規範資料給您配接器的多個執行個體。

該介面是在命名空間的 Compliance.dll 元件中定義的  `Microsoft.Rtc.Internal.Chat.Server.Compliance` 。 此介面定義了您自訂介面卡必須實作的兩種方法。

當配接器第一次載入時，Persistent Chat 規範伺服器會呼叫下列方法。 `AdapterConfig`包含與規範介面卡相關的 Persistent Chat 相容性設定：

```cpp
void SetConfig(AdapterConfig config)
```

只要有要翻譯的新資料，Persistent Chat 規範伺服器便會以週期性的間隔呼叫下列方法。 此時間間隔相當於  `RunInterval` Persistent Chat 規範設定中的設定：

```cpp
void Translate(ConversationCollection conversations)
```

`ConversationCollection`包含上次呼叫此方法時所收集到的交談資訊。

## <a name="customize-the-xslt-definition-file"></a>自訂 XSLT 定義檔案

規範資料會以 XML 形式傳遞，您可以使用 XSLT 定義檔，將其轉換成最適合組織的格式。 本主題說明規範服務所建立的 XML 檔案。 另外也有提供 XSLT 定義及輸出檔範例。

### <a name="output-format"></a>輸出格式

規範服務輸出會依交談分類 (交談元素) ，然後依 message (message 元素) ，如下列程式碼範例所示：

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

Conversation 元素包含四個元素 (Channel、FirstMessage、StartTimeUTC 及 EndTimeUTC)。 Channel 元素包含聊天室的統一資源識別項 (URI)，而 FirstMessage 元素會描述 Messages 元素中的第一則訊息。 StartTimeUTC 和 EndTimeUTC 元素會提供交談的開始時間和結束時間，如下列程式碼範例所示：

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Message 元素包含兩個元素 (Sender 和 DateTimeUTC) 及三個屬性 (Type、Content 和 ID)。 Sender 元素代表傳送郵件的使用者，而 DateTimeUTC 元素表示事件發生的時間，如下列程式碼範例所示：

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

下表說明郵件屬性類型、內容及識別碼。

**Messages 元素屬性**

|**屬性**|**描述**|**選用/必要**|
|:-----|:-----|:-----|
|類型  <br/> |指定訊息類型。訊息類型描述在「訊息元素訊息類型」表格中。  <br/> |必要  <br/> |
|內容  <br/> |包含訊息內容。Type 為 Join 或 Part 的訊息不使用此屬性。  <br/> |選用  <br/> |
|ID  <br/> |指定內容的唯一識別碼。此屬性僅用於 Type 為 Chat 的訊息。  <br/> |選用  <br/> |

每個 Sender 元素都包含五個屬性：user name、ID、email、internal 和 URI。這些屬性的說明如下表。

**Sender 元素屬性**

|**屬性**|**描述**|**選用/必要**|
|:-----|:-----|:-----|
|使用者名稱  <br/> |傳送者的名稱。  <br/> |選用  <br/> |
|ID  <br/> |寄件者的唯一識別碼。  <br/> |必要  <br/> |
|電子郵件  <br/> |寄件者的電子郵件地址。  <br/> |選用  <br/> |
|內部  <br/> |決定使用者為內部使用者或同盟使用者。如果該值設為 true，則為內部使用者。  <br/> |選用  <br/> |
|Uri  <br/> |使用者的 SIP URI。  <br/> |必要  <br/> |

下列範例會顯示 Messages 元素可包含的郵件類型。 其中也提供各元素的用法範例。

Join-使用者加入聊天室。

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Part-使用者離開聊天室。

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

聊天室-寄件者的電子郵件地址。

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat-使用者要求聊天記錄的內容。

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

檔上傳-使用者上傳檔案。

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

檔案下載-使用者下載檔案。

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>預設持續性聊天輸出 XSD 和範例 XSL 轉換

下列程式碼範例包含規範伺服器的預設輸出：

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

下列程式碼範例包含的 XSL 轉換範例：

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
