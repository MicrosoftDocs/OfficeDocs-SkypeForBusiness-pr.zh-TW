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
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器合規性服務。'
ms.openlocfilehash: 95418a814ac8f4796fbde561c90c5ac051c54725
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194067"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>設定常設聊天室伺服器的規範服務

**摘要:** 瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器合規性服務。

持續聊天合規性可讓系統管理員維持持久聊天訊息及活動的封存。 合規性服務會記錄及歸檔與每個持續聊天伺服器交談相關的資料, 包括參與者:

- 加入持久聊天室

- 離開聊天室

- 張貼訊息

- 查看聊天記錄

- 上傳檔案

- 下載檔案

您可以視需要從合規性 SQL 資料庫中檢索此資訊。 

> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>使用 Windows PowerShell 設定合規性服務

使用 [拓撲結構建立器] 啟用合規性服務之後, 您可以使用**CsPersistenChatComplianceConfiguration** Cmdlet 來設定服務:

```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

或

```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

您可以設定下列參數:

- AdapterType-可讓您指定配接器類型。 配接器是協力廠商的產品, 可將合規性資料庫中的資料轉換成特定的格式。 [XML] 是預設值。

- OneChatRoomPerOutputFile-此參數可讓您指定要為每個聊天室建立不同的報表。

- AddChatRoomDetails-啟用時, 此參數會記錄資料庫中每個聊天室的其他詳細資料。 因為此設定會大幅增加資料庫大小, 所以預設為停用。

- AddUserDetails-啟用時, 此參數會記錄資料庫中每個聊天室使用者的其他詳細資料。 因為此設定會大幅增加資料庫大小, 所以預設為停用。

- 身分識別-此參數可讓規範設定成為特定集合的範圍, 包括全域、網站和服務層級。 預設為 [全域] 層級。 

- RunInterval-此參數規定伺服器在建立下一個相容性輸出檔案之前的時間長度 (預設值為15分鐘)。

## <a name="use-a-customized-compliance-adapter"></a>使用自訂的合規性配接器

您可以撰寫自訂配接器, 而不是使用隨持續聊天伺服器一起安裝的 XmlAdapter。 若要完成這項作業, 您必須提供包含實現**IComplianceAdapter**介面之公用類別的 .net Framework 元件。 您必須將此元件放在持續聊天伺服器池中每個伺服器的 [永久聊天伺服器安裝] 資料夾中。 任何一個合規性伺服器都可以為您的配接器提供合規性資料, 但合規性伺服器將不會提供重複的合規性資料給您的配接器的多個實例。

介面是在命名空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`的合規性 .dll 程式集中定義。 介面定義您的自訂配接器必須實現的兩種方法。

當配接器第一次載入時, Persistent 聊天相容性伺服器將呼叫下列方法。 `AdapterConfig`包含與合規性配接器相關的持續聊天相容性設定:

```
void SetConfig(AdapterConfig config)
```

只要有要翻譯的新資料, 持續性聊天規範伺服器就會以週期性的時間間隔呼叫下列方法。 這個時間間隔與持續聊天相容`RunInterval`性設定中的設定相同:

```
void Translate(ConversationCollection conversations)
```

`ConversationCollection`包含上次呼叫此方法時所收集的交談資訊。

## <a name="customize-the-xslt-definition-file"></a>自訂 XSLT 定義檔

合規性資料會以 XML 形式傳送, 您可以使用 XSLT 定義檔, 將其轉換成最符合貴組織的格式。 本主題描述合規性服務所建立的 XML 檔案。 它也提供 XSLT 定義和輸出檔案的範例。

### <a name="output-format"></a>輸出格式

合規性服務輸出是依交談 (交談元素), 然後依訊息 (Messages 元素) 來分類, 如下列程式碼範例所示:

```
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

交談元素包含四個元素 (通道、FirstMessage、StartTimeUTC 和 EndTimeUTC)。 通道元素包含聊天室的統一資源識別項 (URI), 而 FirstMessage 元素則說明 Messages 元素中的第一封郵件。 StartTimeUTC 和 EndTimeUTC 元素會提供交談的開始和結束時間, 如下列程式碼範例所示:

```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Message 元素包含兩個元素 (寄件者與 DateTimeUTC) 和三個屬性 (類型、內容和識別碼)。 Sender 元素代表傳送訊息的使用者, 而 DateTimeUTC 元素則代表事件發生的時間, 如下列程式碼範例所示:

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

下表說明訊息屬性類型、內容和識別碼。

**郵件元素屬性**

|**Attribute**|**說明**|**選擇性/必要**|
|:-----|:-----|:-----|
|類型  <br/> |指定郵件類型。 訊息類型將在 [訊息元素] 訊息類型資料表中說明。  <br/> |必要  <br/> |
|內容  <br/> |包含郵件的內容。 含有連線類型或元件的訊息, 不會使用此屬性。  <br/> |選用  <br/> |
|標識號  <br/> |指定內容的唯一識別碼。 這個屬性只會與聊天類型的訊息搭配使用。  <br/> |選用  <br/> |

每個寄件者元素都包含五個屬性: 使用者名稱、識別碼、電子郵件、內部和 URI。 下表說明這些屬性。

**寄件者元素屬性**

|**Attribute**|**說明**|**選擇性/必要**|
|:-----|:-----|:-----|
|Username  <br/> |寄件者的名稱。  <br/> |選用  <br/> |
|標識號  <br/> |寄件者的唯一識別碼。  <br/> |必要  <br/> |
|電子郵件  <br/> |寄件者的電子郵件地址。  <br/> |選用  <br/> |
|內部  <br/> |判斷使用者是否為內部使用者或同盟使用者。 如果該值設定為 true, 則使用者為 internal。  <br/> |選用  <br/> |
|Url  <br/> |使用者的 SIP URI。  <br/> |必要  <br/> |

下列範例顯示了 Messages 元素可以包含的郵件類型。 它也提供如何使用每個元素的範例。

[加入]-使用者加入聊天室。

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

部分-使用者離開聊天室。

```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

聊天-寄件者的電子郵件地址。

```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat-使用者要求聊天記錄中的內容。

```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

檔案上傳-使用者上傳檔案。

```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

檔案下載-使用者下載檔案。

```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>預設持續聊天輸出 XSD 和範例 XSL 轉換

下列程式碼範例包含合規性伺服器的預設輸出:

```
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

下列程式碼範例包含範例 XSL 轉換:

```
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
