---
title: 在商務用 Skype Server 2015 中規劃 Persistent Chat Server 的高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃 Persistent Chat Server 的高可用性和嚴重損壞修復。
ms.openlocfilehash: 18e5a3e87dae7f65cb8b58788bd1b1b1be02ccc9c6b1f14492cd7da629e5c790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301339"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中規劃 Persistent Chat Server 的高可用性和嚴重損壞修復
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃 Persistent Chat Server 的高可用性和嚴重損壞修復。
  
Persistent Chat Server 的高可用性和嚴重損壞復原需要額外的資源，以超出完整作業的一般需求。 
  
> [!NOTE]
> Persistent Chat Server 資料庫不支援使用 SQL AlwaysOn 可用性群組。 

> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 
  
## <a name="resource-requirements"></a>資源需求

設定持久聊天伺服器以取得高可用性和嚴重損壞修復之前，請先確定您有下列額外資源。 
  
- 一個專用的資料庫實例位於 Persistent Chat Server 服務的主前端所在的相同實體資料中心。 此資料庫將充當主要 Persistent Chat 資料庫的 SQL Server 鏡像。 （選用）如果您想要自動容錯移轉至鏡像資料庫，請指定另一個充當鏡像見證的 SQL Server。
    
- 一個位於其他實體資料中心的專用資料庫實例。 此資料庫會做為主要資料中心中資料庫的 SQL Server 記錄傳送次要資料庫。
    
- 一個專用的資料庫實例充當次要資料庫的 SQL Server 鏡像。 （選用）指定其他 SQL Server 到伺服器做為鏡像見證。 這兩者都必須與次要資料庫位於相同的實體資料中心。
    
- 如果啟用 Persistent Chat Server 相容性，則需要額外三個專用資料庫實例。 其分配與先前對 Persistent 聊天資料庫所述的方式相同。 規範資料庫可以與 Persistent Chat 資料庫共用相同的 SQL Server 實例，但建議使用獨立的高可用性和嚴重損壞修復實例。
    
- 必須建立檔案共用，並為 SQL Server 記錄傳送交易記錄檔指派。 執行持續性聊天資料庫之資料中心的所有 SQL 伺服器都必須具有此檔案共用的讀取/寫入權限。 此共用並未定義為 FileStore 角色的一部分。
    
- 輔助資料庫伺服器上的檔案共用，用作從主要伺服器檔案共用複製之 SQL Server 交易記錄的目的地資料夾。
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>嚴重損壞修復和高可用性解決方案

商務用 Skype Server 支援後端伺服器（包括資料庫鏡像）的多種高可用性模式。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的高可用性和嚴重損壞修復方案](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 
  
本主題中所述 Persistent Chat Server 的嚴重損壞復原解決方案是在延伸的持久聊天伺服器集區上建立。 不需要延伸虛擬區域網路絡 (VLAN) 。 透過拉伸一種 Persistent Chat Server 集區，您可以在不同的拓撲中設定一個集區，但您實際將伺服器集區中的伺服器放在兩個不同的資料中心。 您可以以相同的方式設定資料庫的 SQL Server 鏡像，並在相同的資料中心部署資料庫和鏡像。 您必須在次要資料中心設定備份資料庫 (包含於災害復原期間提供高可用性的選用鏡像)。 此為在災害復原期間用於容錯移轉的備份資料庫。 
  
如需如何為 persistent chat server 設定高可用性和嚴重損壞修復的詳細資訊，請參閱[在商務用 Skype Server 2015 中設定 persistent chat server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。 
  
下圖顯示可在兩個不同的延伸集區拓撲中設定 Persistent Chat Server 集區的方式：
  
- 當資料中心具有高頻寬/低延遲時，延伸的持久聊天伺服器集區。
    
- 資料中心地理位置具有低頻寬/高延遲的延伸 Persistent Chat Server 集區。
    
圖1顯示連續的持久聊天伺服器集區拓撲，其中資料中心的地理位置具有高頻寬/低延遲。 針對邏輯和實體拓撲採用下列各項：
  
- 邏輯拓撲包含下列各項：
    
  - 跨網站1和2的持久聊天集區，包含伺服器1到8。
    
  - 前端伺服器集區、持久聊天資料庫、鏡像資料庫，以及（選擇性） (不會顯示在實際位於網站1上的圖表) 中。 
    
  - 第二部前端伺服器集區和備份資料庫位於網站2的實際位置。
    
- 實體拓撲包含網站1和2，如下所示：
    
  - Persistent Chat 集區，包含伺服器1到4、兩個主動、兩個空閒的網站1。
    
  - Persistent Chat 集區，包含伺服器5到8、兩個主動、兩個空閒的網站2。
    
  - 在網站1上，前端伺服器集區、持久聊天資料庫、鏡像資料庫及（選擇性）的見證資料庫 (不會顯示在圖表) 中。
    
  - 前端伺服器集區，以及備份資料庫，也就是網站2上的 SQL 記錄傳送目標。
    
**資料中心具有高頻寬/低延遲時的延伸 Persistent Chat Server 集區**

![具有高頻寬/低延遲的持續性聊天延伸集區](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
圖2顯示資料中心地理位置具有低頻寬/高延遲的延伸持久聊天伺服器集區拓撲。
  
- 邏輯拓撲包含下列各項：
    
  - 跨網站1和2的持久聊天集區，包含伺服器1到8。
    
  - 前端伺服器集區、持久聊天資料庫、鏡像資料庫，以及（選擇性） (不會顯示在實際位於網站1上的圖表) 中。 
    
  - 第二部前端伺服器集區和備份資料庫位於網站2的實際位置。
    
- 實體拓撲包含網站1和2，如下所示：
    
  - 在網站1上，包含伺服器1到4（所有使用中）的持久聊天集區。
    
  - 在網站2上，包含伺服器5到8，所有空閒的持久聊天集區。
    
  - 在網站1上，前端伺服器集區、持久聊天資料庫、鏡像資料庫及（選擇性）的見證資料庫 (不會顯示在圖表) 中。
    
  - 前端伺服器集區，以及備份資料庫，也就是網站2上的 SQL 記錄傳送目標。
    
**資料中心地理位置具有低頻寬/高延遲的延伸 Persistent Chat Server 集區**

![具有低頻寬/高延遲的持續性聊天延伸集區](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

