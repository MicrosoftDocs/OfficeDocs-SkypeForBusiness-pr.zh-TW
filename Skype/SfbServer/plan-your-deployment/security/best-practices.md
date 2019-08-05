---
title: 商務用 Skype Server 中的核心基礎結構最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 您可能已經採取步驟, 在您的系統中設計容錯能力, 例如確保硬體冗余、防範電源損失、例行安裝安全更新及防病毒措施, 以及監視伺服器活動。 這些做法不僅能獲益您的商務用 Skype 伺服器基礎結構, 還能受益于整個網路。 如果您尚未實現這些做法, 建議您在部署商務用 Skype Server 之前先執行此動作。
ms.openlocfilehash: c1f6a6ebe31276b8dbcd9037fa373baffc055fde
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192950"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>商務用 Skype Server 中的核心基礎結構最佳做法
 
您可能已經採取步驟, 在您的系統中設計容錯能力, 例如確保硬體冗余、防範電源損失、例行安裝安全更新及防病毒措施, 以及監視伺服器活動。 這些做法不僅能獲益您的商務用 Skype 伺服器基礎結構, 還能受益于整個網路。 如果您尚未實現這些做法, 建議您在部署商務用 Skype Server 之前先執行此動作。
  
若要協助保護商務用 Skype Server 部署中的伺服器不受意外或 purposeful 損害, 可能會導致宕機, 請採取下列預防措施:
  
- 使用安全性更新讓伺服器保持在最新狀態。 訂閱 Microsoft Security Notification 服務可協助確保您立即收到任何 Microsoft 產品的安全公告版本通知。 若要訂閱, 請移至[Microsoft 技術安全性通知網站](https://go.microsoft.com/fwlink/p/?LinkId=145202)。
    
- 確定正確設定存取權限。
    
- 讓您的伺服器保持在可避免未經授權存取的實體環境中。 確保您的所有伺服器都安裝了適當的防毒軟體。 使用最新的病毒簽名檔案, 讓軟體保持在最新狀態。 使用防病毒應用程式的自動更新功能, 將病毒簽名保持在最新狀態。
    
- 我們建議您停用您在安裝商務用 Skype Server 的電腦上不需要的 Windows Server 作業系統服務。
    
- 在儲存資料時使用完整容量加密系統來加密作業系統與磁片磁碟機, 除非您能保證對伺服器的持續及完整控制、總物理隔離性, 以及適當且安全地解除取代或失敗的磁片促進.
    
- 停用伺服器的所有外部直接記憶體存取 (DMA) 埠, 除非您能保證嚴格控制伺服器的物理存取權。 DMA (可以相當輕鬆地啟動) 的攻擊會公開非常敏感的資訊, 例如私人加密金鑰。
    

