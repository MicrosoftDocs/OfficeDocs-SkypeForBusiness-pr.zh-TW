---
title: 確認組態設定
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
description: 您可以在中央管理存放區所在的內部電腦上執行商務用 Skype Server 2019 Get-CsManagementStoreReplicationStatus 指令程式，或在已安裝商務用 Skype Server 2019 核心)  (OcsCore.msi 元件的任何已加入網域的電腦上執行 Cmdlet，以驗證將設定資訊複寫至 Edge server。
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335743"
---
# <a name="verify-configuration-settings"></a>確認組態設定

您可以在中央管理存放區所在的內部電腦上，或在已安裝商務用 Skype Server 2019 核心)  (OcsCore.msi 元件的任何已加入網域的電腦上執行商務用 Skype Server 2019 **Get-CsManagementStoreReplicationStatus** Cmdlet，以驗證將設定資訊複寫至 Edge server。 
  
初始結果可能會指出複寫的狀態為「False」，而非「True」。若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus**。 
  

