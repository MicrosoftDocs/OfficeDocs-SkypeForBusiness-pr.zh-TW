---
title: 商務用 Skype Server 核心基礎結構的最佳作法
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 您可能已經採取一些步驟，包括透過確保硬體備份、避免電源中斷、例行性地安裝安全性更新與防毒措施，以及監控伺服器活動等作法，為您的系統設計容錯機制。 這些做法不僅受益于您的商務用 Skype Server 基礎結構，還受益于整個網路。 如果您尚未執行這些做法，建議您在部署商務用 Skype Server 之前執行此操作。
ms.openlocfilehash: 3cd9afbba6014536d146454144456edc91fbf9c0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400234"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>商務用 Skype Server 核心基礎結構的最佳作法
 
您可能已經採取一些步驟，包括透過確保硬體備份、避免電源中斷、例行性地安裝安全性更新與防毒措施，以及監控伺服器活動等作法，為您的系統設計容錯機制。 這些做法不僅受益于您的商務用 Skype Server 基礎結構，還受益于整個網路。 如果您尚未執行這些做法，建議您在部署商務用 Skype Server 之前執行此操作。
  
為了協助保護商務用 Skype Server 部署中的伺服器，避免意外或惡意可能造成停機的損害，請採取下列預防措施：
  
- 隨時注意為伺服器安裝最新的安全性更新。 註冊「微軟資訊安全通知服務」，確保能立即收到任何 Microsoft 產品的資訊安全佈告欄通知。 若要訂閱，請移至 [Microsoft 技術安全性通知網站](https://go.microsoft.com/fwlink/p/?LinkId=145202)。
    
- 確認已正確設定所有的存取權限。
    
- 請將您的伺服器配置於可預防未經授權擅自存取的實體環境。請確認您的伺服器均已安裝適當的防毒軟體。隨時注意安裝最新的病毒碼檔案，保持防毒軟體處於最新狀態。建議您使用防毒應用程式的自動更新功能，來維持最新的病毒碼狀態。
    
- 建議您在安裝商務用 Skype Server 的電腦上停用不需要的 Windows 伺服器作業系統服務。
    
- 為作業系統與磁碟機 (其中資料是以完整磁碟區加密系統存放) 加密，除非您能保證對伺服器能擁有持續及完整的控制、實體隔離總數且能適當與安全地解除委任已取代或故障的磁碟機。
    
- 停用伺服器的所有外部直接記憶體存取 (DMA) 連接埠，除非您能保證對伺服器的實體存取擁有嚴密的控制。 DMA 形式的攻擊通常非常容易啟動，這些攻擊可能會導致高度機密的資訊洩漏，例如私人加密金鑰等。
    

