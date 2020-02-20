---
title: 將 Lync 室系統裝置遷移至 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 請閱讀本主題，瞭解如何將 Lync 室系統裝置遷移至使用 Microsoft 團隊聊天室軟體。
ms.openlocfilehash: 4f0c255c40c64274ff4b104a8706eb8f73ee792f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155105"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>將 Lync 會議室系統（LRS）裝置遷移至 Microsoft 團隊聊天室

使用 Skype 室系統版本1（SRS v1）軟體的 Lync 會議室系統（LRS）裝置已[于2018年10月9日取得支援結束](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)。 這表示 Skype 會議室系統 v1 軟體將不再取得任何產品更新或修正。 如果客戶的裝置是使用 Skype 會議室系統 v1 軟體的 Lync Room System 裝置，建議您將其裝置升級至「Microsoft Teams 會議室」。

Microsoft 團隊會議室軟體除了適用于 Microsoft 團隊之外，還可與 Microsoft 團隊搭配使用，在所有 Microsoft 團隊會議室支援的裝置上進行會議與通話的商務用 Skype。

在 Skype 會議室系統版本1之後，您現有的裝置**可能會**繼續運作。 不過，如果這個軟體遇到需要 Microsoft 釋放修正程式的軟體錯誤，就不會受到支援。 SRS v1 使用的是 TLS 1.0/1.1，在未來將會被 Microsoft 取代。 您可以深入瞭解如何[針對 TLS 1.0/1.1 過時進行準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)。 

## <a name="which-devices-are-affected"></a>哪些裝置會受到影響？

以下是受此變更影響的裝置清單：

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [智慧房間系統](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>升級選項

有多個選項可將 Lync 系統升級至新一代的 Microsoft 團隊會議室。

### <a name="crestron-hardware-trade-in-program"></a>Crestron 硬體外貿程式

Crestron 將針對所有非 Crestron Lync 系統客戶（例如智慧型或 Polycom LRS），提供[CRESTRON SR 系統](https://www.crestron.com/products/featured-solutions/crestron-sr)或對等專案的升級。 請[在](https://support.crestron.com/app/answers/answer_view/a_id/1000220)此查看此程式的詳細資料，或 <!-- For details, -->[電子郵件](mailto:lrsupgrade@crestron.com)Crestron LRS 支援。  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 升級至 Microsoft 團隊聊天室

現有的 Crestron RL2 （也稱為 Crestron RL200）客戶可以取得升級套件，以將目前的 RL2 升級至 RL3，以在每個裝置上使用最低成本。 請[在](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)此查看此程式的詳細資料。

### <a name="smart-room-systems-upgrade"></a>智慧房間系統升級

針對智慧型 LRS 客戶而言，除了 Crestron 硬體交易程式之外，聰明也是提供升級至 Microsoft 團隊聊天室的解決方案。 此升級將由 SMART 技術 Inc. 提供給客戶，以供產品支援人員使用。 請[在](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)此查看更多相關資訊。


## <a name="what-should-you-do"></a>您該怎麼做？

我們建議您先使用上述升級選項，在 TLS 1.0/1.1 過時版本中，將 Lync 室系統裝置更新為 Microsoft 團隊聊天室。 此外，您也可以考慮使用針對 Microsoft 團隊聊天室認證的新裝置來取代現有的裝置。 如需詳細資訊，請參閱[會議室裝置](https://aka.ms/roomdevices)，並查看[Microsoft 團隊會議室需求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  


> [!NOTE]
> Microsoft 團隊聊天室軟體支援 TLS 1.2 通訊協定，在2018中有應用程式版本4.0.64.0 的12月14日。 針對內部部署客戶，在 Microsoft 團隊聊天室啟用經由 TLS 1.2 的通訊需要商務用 Skype Server 2015 累加更新9（CU9）或商務用 Skype Server 2019 累加更新1（CU1）。 因為用戶端變更是轉寄及後相容，所以變更不應該影響商務用 Skype Online 客戶。
