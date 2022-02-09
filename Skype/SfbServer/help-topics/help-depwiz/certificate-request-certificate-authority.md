---
title: 簽署要求 (憑證授權單位)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 將憑證要求傳送到線上憑證授權單位單位 (CA 時)  (通常是內部網路上的伺服器) 上的 [選擇憑證授權單位單位 (CA) ] 頁面上，會顯示兩個選項：
ms.openlocfilehash: eada6d9bade5c5f7c474d4fc340e79b52ad6518b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402267"
---
# <a name="certificate-request-certificate-authority"></a>簽署要求 (憑證授權單位)
 
將憑證要求傳送到線上憑證授權單位單位 (CA 時)  (通常是內部網路上的伺服器) 上的 [ **選擇憑證授權單位單位 (CA)** ] 頁面上，會顯示兩個選項：
  
1. 從環境中偵測到的清單選取 CA。
    
2. 指定另一個憑證授權單位單位。
    
如果您選取第一個選項，您會看到一個下拉式清單，其中包含在您的環境中偵測到的 Windows 所有以伺服器為基礎的憑證授權單位單位。 選取適合您憑證的憑證授權單位單位。 您可能需要與 CA 管理員協商，以瞭解選擇哪個 CA。
  
如果您選取第二個選項，請輸入您要用於憑證之憑證授權單位單位的完整功能變數名稱 (FQDN) 及 CA 實例。 如果您想要使用的 ca 不是 Windows 伺服器型 ca，但可用於 Windows 伺服器型 ca，則此選項是適當的。
  
> [!IMPORTANT]
> 請務必確認您需要成功使用憑證要求的群組成員資格。 通常，憑證授權單位單位具有不同于在伺服器上安裝商務用 Skype Server 的許可權需求。 確認要求您的 CA 管理員要求憑證。 
  

