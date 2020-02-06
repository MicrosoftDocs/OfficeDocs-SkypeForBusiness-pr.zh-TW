---
title: 商務用 Skype Server 中有多個主幹支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server 功能支援閘道與中繼伺服器之間的多個關聯性。 這些關聯是透過定義幹線來建立的，這是中繼伺服器池與公用交換式電話網絡（PSTN）閘道、會話邊界控制器（SBC）或 IP PBX 之間的邏輯關聯。 使用 [拓撲建立器]，將閘道與中繼伺服器（也就是 trunks）建立關聯。
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816943"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>商務用 Skype Server 中有多個主幹支援

商務用 Skype Server 功能支援閘道與中繼伺服器之間的多個關聯性。 這些關聯是透過定義幹線來建立的，這是中繼伺服器池與公用交換式電話網絡（PSTN）閘道、會話邊界控制器（SBC）或 IP PBX 之間的邏輯關聯。 使用 [拓撲建立器]，將閘道與中繼伺服器（也就是 trunks）建立關聯。

- 若要在商務用 Skype Server 中指派或移除主幹，您必須先在拓撲產生器中定義主幹。 主幹包含下列關聯：中繼伺服器的完整功能變數名稱（FQDN）、中繼伺服器偵聽埠、閘道 FQDN，以及閘道偵聽埠。
- 若要設定多個 trunks，您可以在同一個閘道與中繼伺服器之間建立多個關聯性。 這可為企業語音結構提供額外的復原能力，這在私人分支 exchange （PBX） interoperational 案例中特別有用。 

定義主幹時，必須與路由建立關聯。 若要將主幹與路線建立關聯，您可以在 [拓撲建立器] 中定義主幹的簡單名稱。 在商務用 Skype Server [控制台] 中，此簡單名稱會用來做為主幹名稱，其中 trunks 可以與路線建立關聯。 簡單的主幹名稱是從商務用 Skype Server Management Shell 中作為閘道名稱使用。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

系統管理員必須選取與中繼伺服器相關聯的預設主幹。 從拓撲建立器，以滑鼠右鍵按一下關聯的中繼伺服器，然後按一下 [**屬性**]。 指定中繼伺服器的預設閘道。 

下圖說明針對每個中繼伺服器和閘道定義的多個 trunks。 

![多個幹線作業](../../media/multiple-trunk-assignments.jpg)
