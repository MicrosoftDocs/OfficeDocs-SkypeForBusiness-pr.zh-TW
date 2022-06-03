---
title: 安裝商務用 Skype Server的必要條件
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 摘要：瞭解安裝商務用 Skype Server之前必須設定的伺服器和伺服器角色。
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860734"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>安裝商務用 Skype Server的必要條件
 
**總結：** 瞭解安裝商務用 Skype Server之前必須設定的伺服器和伺服器角色。
  
安裝必要條件包含在拓撲中的每部伺服器上安裝必要的角色和功能，以設定 Windows Server。 這些需求是以伺服器在拓撲中將履行的角色為基礎。 您可以依任何循序執行步驟 1 到 5。 不過，您必須依序執行步驟 6、7 和 8，以及步驟 1 到 5 之後，如圖表中所述。 安裝必要條件是步驟 8 的步驟 1。
  
![概觀圖表 - 安裝必要條件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>安裝Windows伺服器

商務用 Skype Server需要Windows伺服器作業系統和一些必要條件才能安裝。 如需規劃必要條件的詳細資訊，請參閱[商務用 Skype Server的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> 此程式使用 Windows Server 2012 R2。 如果您使用不同版本的 Windows Server，則程式可能會稍有不同。 
  
> [!IMPORTANT]
> 開始之前，請使用 Windows Update，確定 Windows Server 是最新的。 
  
![Windows Server 為最新狀態。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
觀看 **安裝必要條件的** 影片步驟：
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>安裝前端伺服器的必要角色和功能

您可以使用 伺服器管理員 來安裝必要的角色和功能。 
    
1. 安裝伺服器需求中所列的[必要商務用 Skype Server](../../../SfBServer2019/plan/system-requirements.md)軟體功能。 必要的軟體必須位於將執行商務用 Skype Server的伺服器上。
    
    > [!CAUTION]
    > Windows Server 2012 R2 預設不會安裝所需功能的所有原始程式檔。 如果伺服器未連線到網際網路，您必須插入 Windows Server 2012 R2 媒體，然後選取 **[指定替代來源路徑**] 以安裝所需的功能。 來源檔案位於 sources\sxs 目錄中。 例如，如果 Windows Server 2012 R2 媒體位於磁片磁碟機 D 中，您會將路徑設定為 `d:\sources\sxs` 。 請務必取得來自 Windows Update 的最新更新。 如果您未連線到網際網路，則必須手動安裝所有相關更新，以及必要更新的任何必要條件。 
  
1. 當對話方塊指出安裝已完成時，您必須重新開機伺服器才能完成此程式。
    
1. 再次 **執行 Windows Update**，以檢查是否已安裝任何角色和服務的更新。
    
1. 如果您將在此伺服器上使用 商務用 Skype Server 主控台，則也必須安裝 Silverlight。 若要安裝 Silverlight，請參閱 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)。


> [!IMPORTANT]
> 執行前端伺服器以外的角色之伺服器的必要條件，例如 Director、Persistent Chat 或 Edge 的角色，都有自己的必要條件。 如需每個伺服器類型所需之確切必要條件的詳細資訊，請參閱[商務用 Skype Server的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。 
  

