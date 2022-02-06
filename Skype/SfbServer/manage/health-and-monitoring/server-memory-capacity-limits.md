---
title: 監視商務用 Skype Server 中的伺服器記憶體容量限制
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要：瞭解如何監視商務用 Skype Server 中的伺服器記憶體容量限制。
---

# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>監視商務用 Skype Server 中的伺服器記憶體容量限制
 
**總結：** 瞭解如何監視商務用 Skype Server 中的伺服器記憶體容量限制。
  
> [!CAUTION]
> 本主題所述的容量規劃的資訊僅適用于 Lync 2010 行動用戶端和行動服務 (Mcx) 。 Lync Server 2013 （計畫工具）提供的整合通訊網頁 API (UCWA) （供 Lync 2013 行動用戶端使用）的容量規劃。 

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
兩個行動效能計數器可協助您判斷目前的使用狀況，並協助您規劃商務用 Skype Server 行動性服務 (Mcx) 的容量，並監視 UCWA 的記憶體使用量。 針對 UCWA，計數器類別為 **LS： WEB UCWA**。 針對行動服務 (Mcx) ，計數器位於類別 **LS： WEB Mobile Communication Service**。 要監視的計數器包括：
  
- **目前使用中的會話計數與使用中狀態訂閱**，這是透過 UCWA 所註冊的端點數目，也就是具有使用中狀態訂閱的行動 (服務) ， (永不連線的行動使用者數目) 
    
- 目前使用中的 **會話計數**，也就是透過 UCWA 或行動性服務註冊的目前端點數目
    
如果 **目前使用中狀態訂閱** 和目前作用中的會話計數之間的差異， **目前的會話計數** 很小，這表示大多數行動裝置使用者都有一個永不連線的裝置，例如 Android 或 Nokia mobile Device (僅限 Mcx) 。 UCWA always 連裝置，包括執行 Lync 2013 行動用戶端) 的 Apple 和 Android 裝置。 如果目前作用中的 **會話計數** 比 **目前使用中狀態訂閱目前使用中的會話計數** 高，這表示有更多使用者正在使用背景端點裝置，例如 Apple iOS 裝置或 Mcx 下的 Windows Phone。  (Windows Phone 是唯一會以此) 註冊的 Lync 2013 行動用戶端。
  
您應該根據預期的使用量、容量規劃結果，以及即時監控行動性服務和其他前端伺服器計數器，來設定目前作用中的 **會話計數與使用中狀態訂閱** 及目前使用中 **會話計數** 效能計數器的限制。 您設定的限制應可讓您評估伺服器容量，並在超出容量時引發警示。
  
若要判斷適當的限制，您必須先決定可在行動服務的前端伺服器上使用多少記憶體。 根據下列公式，監視計數器，以判斷何時需要規劃額外的容量：
  
Mcx 行動性服務使用的總記憶體 (MB) = 164 + (400 + 134) /1024 ***目前使用中的會話計數與使用中的目前狀態訂閱**+ 400/1024 * (**目前**  -  作用中的會話計數 **目前使用中狀態訂閱目前使用中的會話計數**) 
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 容量計算機是預先填入的試算表，其可讓規劃人員判斷商務用 Skype 伺服器（包括 CPU、記憶體和硬碟）的需求。 您可以 [下載試算表和相關聯的檔](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
前端伺服器需要足夠的可用記憶體，以在容錯移轉的情況下支援行動性服務。 您可以使用 **Memory\Available mb** 的計數器（或先前所述的方程式）來監視前端伺服器上目前可用的記憶體，以規劃預期行動服務所要使用的記憶體量。
  
若當您規劃預期的行動使用者數目時，前端伺服器上可用的記憶體量低於 1500 MB，您需要新增更多硬體以支援行動性服務。 如需詳細資訊，請參閱 Operations 檔中的[監視行動性以取得效能商務用 Skype Server](monitor-mobility-performance.md) 。
  
## <a name="see-also"></a>另請參閱

[監視行動性以取得商務用 Skype Server 效能](monitor-mobility-performance.md)
