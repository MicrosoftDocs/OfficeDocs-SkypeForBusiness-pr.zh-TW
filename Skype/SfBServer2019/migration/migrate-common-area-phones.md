---
title: 遷移常見的區域電話
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 常見的區域手機是最常位於共用工作區或常見區域 (例如大廳、廚房或工廠地面) 的 IP 電話。 常見的區域電話不需要連線到電腦, 就能供應商務用 Skype Server 整合通訊 (UC) 功能。 將部署遷移到商務用 Skype Server 2019 之後, 您也必須遷移與舊版常見區域手機相關聯的連絡人物件。 使用商務用 Skype Server 管理命令介面, 您將會先檢索與舊版常用區域手機相關的所有連絡人物件, 然後將這些物件移到商務用 Skype Server 2019 池。
ms.openlocfilehash: 915b0b86c4f0b1ac74e2575cdfcd65d0cbf23d31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189079"
---
# <a name="migrate-common-area-phones"></a>遷移常見的區域電話

常見的區域手機是最常位於共用工作區或常見區域 (例如大廳、廚房或工廠地面) 的 IP 電話。 常見的區域電話不需要連線到電腦, 就能供應商務用 Skype Server 整合通訊 (UC) 功能。 將部署遷移到商務用 Skype Server 2019 之後, 您也必須遷移與舊版常見區域手機相關聯的連絡人物件。 使用商務用 Skype Server Management 命令介面, 您將會先檢索與舊版常見區域手機相關的所有連絡人物件, 然後將這些物件移到商務用 Skype Server 2019 池。
  
### <a name="migrate-common-area-phones"></a>遷移常見的區域電話

1. 從商務用 Skype Server 2019 前端伺服器, 開啟商務用 Skype Server 管理命令介面。
    
2. 在命令列中, 輸入下列內容:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 若要確認所有連絡人物件都已移至商務用 skype Server 2019, 請從商務用 Skype Server 管理命令介面輸入下列內容:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    確認所有連絡人物件現在都與商務用 Skype Server 2019 池相關聯。
    

