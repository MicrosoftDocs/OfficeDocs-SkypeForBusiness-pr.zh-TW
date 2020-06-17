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
description: 您可以在中央管理存放區所在的內部電腦上，或在已安裝商務用 Skype Server 2019 核心元件（OcsCore.msi）的任何已加入網域的電腦上執行商務用 Skype Server 2019 Get-CsManagementStoreReplicationStatus Cmdlet，以驗證設定資訊的複寫至 Edge server。
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752145"
---
# <a name="verify-configuration-settings"></a>確認組態設定

您可以在中央管理存放區所在的內部電腦上，或在已安裝商務用 Skype Server 2019 核心元件（OcsCore.msi）的任何已加入網域的電腦上執行商務用 Skype Server 2019 **Get-CsManagementStoreReplicationStatus** Cmdlet，以驗證設定資訊的複寫至 Edge server。 
  
初始結果可能會指出複寫的狀態為 "False"，而非 "True"。 若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus**。 
  

