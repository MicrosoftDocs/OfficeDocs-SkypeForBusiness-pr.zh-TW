---
title: 監視商務用 Skype Server 中的伺服器記憶體容量限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要：瞭解如何監視商務用 Skype Server 中的伺服器記憶體容量限制。
ms.openlocfilehash: 4f56fec8f3ed6900f4c4f1a97286dc14b66bb7c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817702"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>監視商務用 Skype Server 中的伺服器記憶體容量限制
 
**摘要：** 瞭解如何在商務用 Skype Server 中監視伺服器記憶體容量限制。
  
> [!CAUTION]
> 本主題中參照容量規劃的資訊，只適用于 Lync 2010 行動用戶端和行動服務（Mcx）。 Lync 2013 行動用戶端所使用之整合通訊網頁 API （UCWA）的容量規劃是由 Lync Server 2013、規劃工具所提供。 

> [!NOTE]
> MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
兩個行動效能計數器可協助您判斷目前的使用方式，並協助您規劃商務用 Skype Server 行動服務（Mcx）的容量，以及監視 UCWA 的記憶體使用量。 針對 UCWA，計數器類別是**LS： WEB-UCWA**。 針對行動服務（Mcx），計數器位於類別**LS： WEB Mobile 通訊服務**。 要監視的計數器包括：
  
- **目前使用中的目前狀態訂閱的目前活動會話計數**，也就是透過 UCWA 或行動服務（Mcx）提供作用中的目前狀態訂閱（永不連線的行動使用者數目）
    
- 目前使用中的**會話計數**，是透過 UCWA 或行動服務註冊的目前端點數目
    
如果**目前使用中的目前狀態訂閱與**目前的**活動會話計數**之間的差異在一段時間內很小，這表示大多數行動裝置使用者都有一個永不連線的裝置，例如 Android 或 Nokia 行動裝置（僅適用于 Mcx）。 UCWA [永不連線的裝置] 包括執行 Lync 2013 行動用戶端的 Apple 和 Android 裝置。 如果**目前的活動會話計數**比目前使用中**的目前狀態訂閱**要高許多，這表示您的使用者使用的是背景端點裝置，例如 Apple iOS 裝置或 Mcx 下的 Windows Phone。 （Windows Phone 是唯一的 Lync 2013 行動用戶端，會以這種方式註冊）。
  
您應該根據預期使用量、容量規劃結果，以及持續監視行動服務與其他前端伺服器計數器，來針對**目前使用中的會話計數**以及**目前的活動會話計數**效能計數器來設定限制。 您設定的限制應該能讓您評估伺服器容量，並在超過容量時引發警示。
  
若要判斷適當的限制，您必須先決定可在行動服務的前端伺服器上使用多少記憶體。 根據下列公式監視計數器，以判斷您何時需要規劃額外的容量：
  
Mcx 行動服務（MB）所使用的記憶體總量 = 164 + （400 + 134）/1024 ***目前處於使用中狀態訂閱的活動會話數**+ 400/1024 * （**目前** - 作用中的會話計數**目前使用中的目前狀態訂閱**）
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 容量計算機是預先填入了所有公式的試算表，可讓 planner 判斷商務用 Skype 伺服器（包括 CPU、記憶體及硬碟）的需求。 您可以[下載試算表及相關聯的檔](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
前端伺服器需要足夠的可用記憶體，才能在容錯移轉情況下支援行動服務。 您可以使用**Memory\Available mb**計數器監視前端伺服器上目前可用的記憶體，或使用先前所述的方程式，來規劃預期行動服務要使用的記憶體量。
  
如果在您規劃預期的行動使用者數量時，前端伺服器上可用的記憶體量低於 1500 MB，您需要新增更多硬體來支援行動服務。 如需詳細資訊，請參閱在作業檔中[監視商務用 Skype 伺服器的效能](monitor-mobility-performance.md)。
  
## <a name="see-also"></a>另請參閱

[監視行動在商務用 Skype Server 中的效能](monitor-mobility-performance.md)
