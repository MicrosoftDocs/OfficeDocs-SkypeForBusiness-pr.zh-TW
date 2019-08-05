---
title: 常設聊天室伺服器清單表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: 持續聊天資料庫架構是由下清單格所組成。
ms.openlocfilehash: 6a6c0bc2c2cc2d5e5ba59f9f636ed9cea2189bed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192767"
---
# <a name="list-of-persistent-chat-server-tables"></a>常設聊天室伺服器清單表格
 
持續聊天資料庫架構是由下清單格所組成。
  
## <a name="active-directory-sync"></a>Active Directory 同步處理

|**表格**|**說明**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |包含目前的輕型目錄存取通訊協定 (LDAP) 同步處理 cookie。 每個資料列都會對應到一個 Active Directory 網域服務網域, 持久聊天伺服器會積極監視所做的變更。 (只有與持久聊天伺服器相關的 Active Directory 網域才會顯示在這個表格中。)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |包含尚未由後續 Active Directory 同步處理步驟處理的群組成員資格變更 (已新增和移除的成員), 而且是 Active Directory 同步處理第一個步驟中所使用的其中一個臨時資料表 (以及 tblADUpdates 資料表)。  <br/> 成員資格變更只會儲存在 tblPrincipal 資料表中所列的群組中, 或在其中已列出成員。  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |包含對 Active Directory 網域服務所做的變更, 這些變更尚未由後續的 Active Directory 同步處理步驟所處理, 而且是 Active Directory 第一個步驟中所使用的其中一個臨時資料表 (以及 tblPrincipalMemberDifference 資料表)非同步.  <br/> 對 Active Directory 所做的變更只會儲存在 tblPrincipal 資料表中所列的主體中, 或同時進行處理。  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |包含主體成員資格。  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |包含必須從 Active Directory 進行更新的主體。  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |包含無法因某種原因而重新整理的隸屬關係, 通常是因為 Active Directory 存取錯誤。  <br/> 此表格僅供提供資訊之用途。 不會使用其內容。  <br/> 具有無法正確更新之隸屬關係的主體會保留在 tblPrincipalMeta 資料表中, 並會提供另一個機會進行重新整理。  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>主體、隸屬關係、節點、範圍和角色

|**表格**|**說明**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |包含對 tblPrincipal 資料表中的內容進行分類的主要類型。 此資料表是靜態的。 它是在資料庫建立期間設定, 不會變更。  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |包含所有主體 (使用者、資料夾、群組等)。 持續性聊天伺服器會將它處理為平面異類清單。 各種資料行都是以每個主體的類型為基礎。  <br/> 大多數的主體都是儲存在 Active Directory 中的物件的快取複本。 在這些 Active Directory 物件的主要目錄中建立快取複本的參照稱為 [預配]。  <br/> 有些原則的建立比其他人更主動, 且某些 Active Directory 物件會完全忽略。  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |包含描述 Active Directory 安全性群組中的成員資格、Active Directory 容器等的主體隸屬關係。  <br/> |
|[tblNode](tblnode.md) <br/> |包含 [控制台] 中所管理的類別節點。  <br/> |
|[tblRoleType](tblroletype.md) <br/> |包含角色類型及其相關聯的許可權集。 這個查閱表格是靜態的。  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |包含指派給節點的範圍。  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |包含指派給節點的角色。  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |包含可與節點相關聯的已註冊增益集。  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |只包含在 tblNode 資料表中使用的硬式 "可見度" 和 "行為" 屬性。  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |包含 tblNode 資料表中所使用的硬編碼 "可見度" 和 "行為" 屬性的值。  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>邀請、聊天及其他用戶端支援

|**表格**|**說明**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |在系統中包含已啟用自動邀請的所有節點的所有已預配使用者的邀請。  <br/> |
|[tblChat](tblchat.md) <br/> |包含所有聊天訊息。  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |包含每位使用者所產生 (並在 tblPrincipalInvites 資料表中使用) 的上一個邀請 ID。  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |包含每位使用者所產生 (並在 tblChat 資料表中使用) 的最後一個聊天 ID。  <br/> |
|[tblPreference](tblpreference.md) <br/> |包含使用者用戶端喜好設定 (僅供舊版用戶端使用)。  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |包含用於檔案傳輸用途的臨時權杖。 每次上傳或下載檔案時, Persistent 聊天服務會產生一個權杖供用戶端用來存取 Web 服務檔存放區。  <br/> |
   
## <a name="server-support"></a>伺服器支援

|**表格**|**說明**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |包含持續聊天伺服器池中的作用中伺服器。  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |包含管理員鎖, 可執行某些系統管理員命令。 TblSystemRevision 資料表中的系統修訂專案會在每次解除鎖定之後增加。  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |包含所使用的修訂數輸入 (以及 tblAdminLock 資料表), 以在多個伺服器間保持一致性。  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |包含持續聊天服務之間的目前對等連線。  <br/> |
|[tblConfig](tblconfig.md) <br/> |包含持續聊天伺服器不支援的設定。  <br/> |
   

