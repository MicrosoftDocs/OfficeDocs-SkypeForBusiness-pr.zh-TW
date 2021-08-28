---
title: 常設聊天室伺服器表格清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Persistent Chat 資料庫架構是由下清單格所組成。
ms.openlocfilehash: 2d5accc32b01c4c854fc3603e4ec3c1dc61a115b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606032"
---
# <a name="list-of-persistent-chat-server-tables"></a>常設聊天室伺服器表格清單
 
Persistent Chat 資料庫架構是由下清單格所組成。
  
## <a name="active-directory-sync"></a>Active Directory 同步處理

|**表格**|**描述**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |包含目前的輕量目錄存取通訊協定 (LDAP) Sync cookie。 每一列都對應到 Persistent Chat Server 主動監控變更的 Active Directory 網域服務網域。 在此表格中只會顯示與 Persistent Chat Server 相關之 Active Directory 網域的 (。 )   <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |包含的群組成員資格變更 (新增及移除的成員) 尚未由後續的 Active Directory 同步步驟處理，也就是其中一個臨時資料表 (以及 Active Directory 同步處理第一個步驟中所用 tblADUpdates 表) 。  <br/> 僅針對 tblPrincipal 表格中所列或具有已提列成員的群組，存放及/或處理其成員資格變更。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |包含尚未由後續 Active Directory 同步步驟處理的 Active Directory 網域服務變更，也就是其中一個臨時表格 (，以及 Active Directory 同步處理第一個步驟中所用的 tblPrincipalMemberDifference 表格) 。  <br/> 對於已列于 tblPrincipal 表格中的主體，會儲存、處理或處理 Active Directory 的變更。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |包含主體成員資格。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |包含必須從 Active Directory 重新整理的主體。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |包含因某些原因而無法重新整理的隸屬關係，通常是因為 Active Directory 存取錯誤。  <br/> 本表格之用途僅為提供資訊參考用。其內容無法使用。  <br/> tblPrincipalMeta 表格中會存放具有無法正確重新整理之關係的主體，並給予其另一次重新整理的機會。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主體、關係、節點、範圍與角色

|**表格**|**描述**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |含有主體類型以分類 tblPrincipal 表格中的項目。此表格是靜態的，其會在資料庫建立期間設定，且不會變更。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |內含所有主體，包括使用者、資料夾及群組等。 Persistent Chat Server 會以平坦的異類清單形式處理此。 各欄位會依據每個主體的類型而定。  <br/> 大多數的主體是儲存在 Active Directory 中之物件的快取複本。 在這些 Active Directory 物件的主體表格中建立快取複本，稱為布建。  <br/> 有些主體的建立會比其他主體更主動，而且會完全忽略某些 Active Directory 物件。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |包含主體隸屬關係，描述 Active Directory 安全性群組、Active Directory 容器等等中的成員資格。  <br/> |
|[tblNode](tblnode.md) <br/> |包含在 [控制台] 中管理的類別節點。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |是一種靜態查閱表格，含有角色類型與其相關的權限組。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |包含指派給節點的範圍。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |包含指派給節點的角色。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |包含可與節點相關聯的已註冊增益集。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |僅包含 tblNode 表格中所用之「可見度」和「行為」硬式編碼屬性。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |包含 tblNode 表格中所用的已編碼 "Visibility" 和 "Behavior" 屬性值。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>邀請、聊天以及其他用戶端支援

|**表格**|**描述**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |包含系統中所有啟用自動邀請的節點之所有已佈建使用者的邀請。  <br/> |
|[tblChat](tblchat.md) <br/> |包含所有聊天訊息。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |含有為每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |含有為每個使用者產生 (也用於 tblChat 表格) 的最後一個聊天 ID。  <br/> |
|[tblPreference](tblpreference.md) <br/> |包含使用者用戶端喜好設定 (僅限舊版用戶端使用)。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |包含用於檔案傳輸的臨時權杖。 每次上傳或下載檔案時，Persistent 聊天服務都會產生一個權杖，用戶端會使用該權杖來存取 Web 服務檔案存放區。  <br/> |
   
## <a name="server-support"></a>伺服器支援

|**表格**|**描述**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |包含 Persistent Chat Server 集區中的主動伺服器。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |包含執行某些管理員命令所需的管理員鎖定。tblSystemRevision 表格中的系統修訂項目會在每次解除鎖定後遞增。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |包含所用的修訂編號項目 (搭配 tblAdminLock 表格) 以用於封存多部伺服器間的一致性。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |包含 Persistent Chat service 之間目前的對等連線。  <br/> |
|[tblConfig](tblconfig.md) <br/> |包含 Persistent Chat Server 不支援的設定。  <br/> |
   

