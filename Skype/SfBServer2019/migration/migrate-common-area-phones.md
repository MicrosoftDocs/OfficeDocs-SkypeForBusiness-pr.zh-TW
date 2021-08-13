---
title: 移轉公共區域電話
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 公共區域電話為最常在共用工作區或公共區域 (例如大廳、廚房或工廠) 的 IP 電話。 一般區域電話不需要連線到電腦，就能供應商務用 Skype Server 的整合通訊 (UC) 功能。 將部署遷移至商務用 Skype Server 2019 之後，您還必須遷移與舊版通用區域相關聯的連絡人物件電話。 使用商務用 Skype Server 管理命令介面您會先取得與舊版公用區域電話相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。
ms.openlocfilehash: 808e874216fac97b01face6efa7aae00e269b74ee0f009b106f872a33a6d6261
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340429"
---
# <a name="migrate-common-area-phones"></a>移轉公共區域電話

公共區域電話為最常在共用工作區或公共區域 (例如大廳、廚房或工廠) 的 IP 電話。 一般區域電話不需要連線到電腦，就能供應商務用 Skype Server 的整合通訊 (UC) 功能。 將部署遷移至商務用 Skype Server 2019 之後，您還必須遷移與舊版通用區域相關聯的連絡人物件電話。 使用商務用 Skype Server 管理命令介面，您會先找回與舊版公用區域電話相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。
  
### <a name="migrate-common-area-phones"></a>移轉公共區域電話

1. 從商務用 Skype Server 2019 前端伺服器，開啟商務用 Skype Server 管理命令介面。
    
2. 從命令列輸入下列命令：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 若要確認已將所有連絡人物件移至商務用 Skype Server 2019 集區，請從商務用 Skype Server 管理命令介面輸入下列命令：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    確認所有連絡人物件現在已與商務用 Skype Server 2019 集區相關聯。
    

