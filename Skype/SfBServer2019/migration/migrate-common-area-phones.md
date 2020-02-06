---
title: 移轉公共區域電話
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 常見的區域手機是最常位於共用工作區或常見區域（例如大廳、廚房或工廠地面）的 IP 電話。 常見的區域電話不需要連線到電腦，就能供應商務用 Skype Server 整合通訊（UC）功能。 將部署遷移到商務用 Skype Server 2019 之後，您也必須遷移與舊版常見區域手機相關聯的連絡人物件。 使用商務用 Skype Server 管理命令介面，您將會先檢索與舊版常用區域手機相關的所有連絡人物件，然後將這些物件移到商務用 Skype Server 2019 池。
ms.openlocfilehash: 5110f91788d09f644e20680f91f1cbafe146bdd6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813561"
---
# <a name="migrate-common-area-phones"></a>移轉公共區域電話

常見的區域手機是最常位於共用工作區或常見區域（例如大廳、廚房或工廠地面）的 IP 電話。 常見的區域電話不需要連線到電腦，就能供應商務用 Skype Server 整合通訊（UC）功能。 將部署遷移到商務用 Skype Server 2019 之後，您也必須遷移與舊版常見區域手機相關聯的連絡人物件。 使用商務用 Skype Server Management 命令介面，您將會先檢索與舊版常見區域手機相關的所有連絡人物件，然後將這些物件移到商務用 Skype Server 2019 池。
  
### <a name="migrate-common-area-phones"></a>移轉公共區域電話

1. 從商務用 Skype Server 2019 前端伺服器，開啟商務用 Skype Server 管理命令介面。
    
2. 在命令列中，輸入下列內容：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 若要確認所有連絡人物件都已移至商務用 skype Server 2019，請從商務用 Skype Server 管理命令介面輸入下列內容：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    確認所有連絡人物件現在都與商務用 Skype Server 2019 池相關聯。
    

