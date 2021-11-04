---
title: 憑證要求 (已傳回)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 「線上憑證要求狀態」頁面會顯示因成功建立和發行線上憑證要求而產生的重要資訊。 此頁面提供可唯一識別憑證的憑證指紋。 依預設，此核取方塊會選取此憑證，以選取 [商務用 Skype Server 憑證使用方式]。 如果您按一下 [完成]，會自動將憑證指派給商務用 Skype Server，以供您在建立憑證要求的步驟期間定義的目的。 根據預設，指派憑證的用途如下：
ms.openlocfilehash: 7f92c95fa5d1588d7563791dca38da46c550048b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740049"
---
# <a name="certificate-request-returned"></a>憑證要求 (已傳回)
 
「線上憑證要求狀態」頁面會顯示因成功建立和發行線上憑證要求而產生的重要資訊。 此頁面提供可唯一識別憑證的憑證指紋。 依預設，此核取方塊會選取 **此憑證，以選取 [商務用 Skype Server 憑證使用** 情況]。 如果您按一下 **[完成]**，會自動將憑證指派給商務用 Skype Server，以供您在建立憑證要求的步驟期間定義的目的。 根據預設，指派憑證的用途如下：
  
- 對相互傳輸層安全性 (MTLS) 連線至用戶端和其他伺服器的伺服器預設值
    
- Web 服務內部-內部 Web 服務網站上的內部用戶端和伺服器連線，用於傳輸層安全性/安全通訊端層 (TLS/SSL) 
    
- 用於 TLS/SSL 的外部 Web 服務網站上的 Web 服務外部用戶端和伺服器連線
    
按一下 [檢視憑證詳細資料] 來檢視憑證，以確認憑證的內容符合預期，且憑證已可套用並運用在伺服器上。
  
按一下 [完成] 以完成線上憑證要求程序。 如果您選取 [**將此憑證指派給商務用 Skype Server 憑證使用** 情況] 核取方塊，則會自動指派該憑證。 如果您選擇清除此核取方塊，您必須在不同步驟中指派憑證。 
  
> [!IMPORTANT]
> 如果憑證授權單位單位 (CA) 根憑證不在電腦的受信任的憑證授權單位單位存放區中，或中級 CA 憑證不在適當的存放區中，您將會看到摘要狀態，如下圖所示。 您沒有指派憑證的餘地。 若要完成憑證指派程序，您必須匯入簽發的 CA 的根憑證和任何中繼 CA 憑證，然後按一下 [憑證精靈] 主要頁面上的 [指派] 來指派憑證。
  

