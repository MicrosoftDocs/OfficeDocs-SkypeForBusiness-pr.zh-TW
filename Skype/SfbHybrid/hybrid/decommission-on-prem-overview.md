---
title: 解除您的內部部署商務用 Skype 環境
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 如何解除委任內部部署商務用 Skype 環境的指示。
ms.openlocfilehash: 0f1b25c6960739992913f31a89a9f554fb180e949df3e6dd213b5fbe14c4af82
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280348"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>解除您的內部部署商務用 Skype 環境

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

如果您的組織使用 Teams 搭配內部部署商務用 Skype Server，您可以將這些環境完整遷移至雲端，然後淘汰商務用 Skype Server 的內部部署。 

> [!NOTE]
> 在解除委任內部部署環境之前，您必須[設定](configure-hybrid-connectivity.md)內部部署和 Microsoft 365 之間的混合式連線。 設定混合式連線後，您可以將使用者遷移至雲端，同時從內部部署遷移其會議，以及將任何連絡人從商務用 Skype Server 遷移至 Teams。 設定混合式連線是將使用者從內部部署遷移至雲端的必要步驟，以確保完整的 Teams 功能。

若要完成從內部部署到雲端的移動，並解除委任您的內部部署商務用 Skype Server 環境，您必須依下列順序完成下列步驟：

- **步驟1。** [將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)。

- **步驟2。** [停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。

- **步驟3。** [將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)。

- **步驟4。** [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。

