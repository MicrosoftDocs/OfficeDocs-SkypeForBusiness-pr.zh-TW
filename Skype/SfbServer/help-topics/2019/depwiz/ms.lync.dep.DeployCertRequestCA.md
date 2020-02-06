---
title: 憑證要求 (憑證授權單位)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 在 [選擇憑證授權單位 (CA)] 頁面上向線上憑證授權單位 (CA) (通常是您內部網路上的伺服器) 提出憑證申請時，您會看到兩個選項：
ms.openlocfilehash: 6c52a46bf40211d05ea47205d2573627910d3ba6
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796754"
---
# <a name="certificate-request-certificate-authority"></a>憑證要求 (憑證授權單位)
 
在 [選擇憑證授權單位 (CA)]**** 頁面上向線上憑證授權單位 (CA) (通常是您內部網路上的伺服器) 提出憑證申請時，您會看到兩個選項：
  
1. 從環境中偵測到的清單選取 CA。
    
2. 指定另一個憑證授權單位。
    
如果您選取第一個選項，您會看到一個下拉式清單，其中包含在您的環境中偵測到的所有 Windows Server 認證授權機構。 選取適合您憑證的憑證授權單位。 您可能需要詢問 CA 系統管理員，以了解應該選擇的 CA。
  
如果您選取第二個選項，請輸入憑證授權單位的完整網域名稱 (FQDN) 和 CA 執行個體，以用於您的憑證。如果您要使用的 CA 不是 Windows Server CA，則適合選取此選項，但 Windows Server CA 也適用。
  
> [!IMPORTANT]
> 請務必確認您需要具備的群組成員資格，以便成功提出憑證申請。 通常，憑證授權單位會根據在伺服器上安裝商務用 Skype Server 的需求，提供不同的許可權需求。 請向 CA 系統管理員確認申請憑證時的需求。 
  

