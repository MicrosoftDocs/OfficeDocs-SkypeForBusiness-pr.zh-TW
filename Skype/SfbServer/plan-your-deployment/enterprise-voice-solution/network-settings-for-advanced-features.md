---
title: 商務用 Skype Server 中的 [高級企業語音功能] 的網路設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: 瞭解網路區域、網路網站和 IP 子網。 所有這些都必須設定為在商務用 Skype 中針對媒體旁路部署方案、規劃商務用 Skype Server 中的通話許可控制，或在商務用 Skype Server 企業版的商務用 Skype 伺服器中規劃緊急服務。
ms.openlocfilehash: 25987630ae2082ca8805d87a988760296637d3f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802593"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>商務用 Skype Server 中的 [高級企業語音功能] 的網路設定

瞭解網路區域、網路網站和 IP 子網。 所有這些都必須設定為[在商務用 skype 中針對媒體旁路部署方案](media-bypass.md)、[規劃商務用 skype server 中的通話許可控制](call-admission-control.md)，或在商務用 skype Server 企業版的[商務用 skype 伺服器中規劃緊急服務](emergency-services.md)。

商務用 skype 伺服器有三個高級企業語音功能：[在商務用 Skype server 中規劃通話許可控制](call-admission-control.md)、[規劃商務用 skype server 中的緊急服務](emergency-services.md)，以及[規劃在商務用 skype 中旁路媒體](media-bypass.md)。 這些功能會在商務用 Skype 伺服器拓撲結構中，與網路網站共用網路區域、網路網站和每個子閘道聯的特定配置需求。

本主題概述這三個高級企業語音功能通用的配置需求。

## <a name="network-regions"></a>網路區域

網路區域是網路中樞或網路骨幹，只能在通話許可控制（CAC）、E9-1 及媒體旁路設定中使用。

> [!NOTE]
> 網路區域與商務用 Skype Server 電話撥入式會議區域不一樣，這是將電話撥入式會議存取號碼與一個或多個商務用 Skype Server 撥號方案關聯所需的專案。 如需電話撥入式會議區域的詳細資料，請參閱[規劃電話撥入式會議](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx)。

CAC 需要每個網路區域都有一個相關聯的商務用 Skype Server 中央網站，可管理該區域內的媒體流量（亦即根據您已設定的原則作出決定），關於是否有即時音訊或您可以建立視頻會話。 商務用 Skype Server 中央網站不代表地理位置，而是設定為一個池或一組池的邏輯伺服器群組。

若要設定網路區域，您可以使用商務用 Skype Server [控制台] 的 [**網路**設定] 區段上的 [**區域**] 索引標籤，或執行**新的 CsNetworkRegion**或**CsNetworkRegion**商務用 skype server Management Shell Cmdlet。 如需相關指示，請參閱在部署檔中[部署商務用 skype 中的網路區域、網站和子網](../../deploy/deploy-enterprise-voice/deploy-network.md)，或參閱商務用 Skype Server Management 命令介面檔。

所有三個高級企業語音功能都將共用相同的網路區域定義。 如果您已經為一個功能建立了網路區域，就不需要為其他功能建立新的網路區域。 不過，您可能需要修改現有的網路區域定義，才能套用特定功能的設定。 例如，如果您已建立 E9 的網路區域（不需要關聯的中央網站），且稍後您要部署 [呼叫許可控制]，則您必須修改每個網路區域定義，才能指定中央網站。

若要將商務用 Skype Server 中央網站與網路區域建立關聯，您可以指定中心網站名稱，方法是使用商務用 Skype Server [控制台] 的 [**網路**設定] 區段，或執行**新的 CsNetworkRegion**或**CsNetworkRegion** Cmdlet。 如需相關指示，請參閱在部署檔中[部署商務用 skype 中的網路區域、網站和子網](../../deploy/deploy-enterprise-voice/deploy-network.md)，或參閱商務用 Skype Server Management 命令介面檔。

## <a name="network-sites"></a>網路網站

Network 網站代表地理位置，例如分支機搆、地區辦事處或主辦公室。 每個網路網站都必須與特定的網路區域建立關聯。

> [!NOTE]
> 網路網站只能由高級企業語音功能使用。 它們與您在商務用 Skype Server 拓撲結構中設定的分支網站不同。

若要設定網路網站並將它與網路區域建立關聯，您可以使用商務用 Skype Server [控制台] 的 [**網路**設定] 區段，或執行商務用 Skype Server Management Shell **CsNetworkSite**或**CsNetworkSite** Cmdlet。 如需詳細資訊，請參閱在部署檔中[建立或修改網路網站](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)，或參閱商務用 Skype Server Management 命令介面檔。

## <a name="identify-ip-subnets"></a>識別 IP 子網

針對每個網路網站，您必須與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。 如果您的網路系統管理員已經將 IP 子網組織到網路區域和網路網站，您的工作會明顯簡化。

例如，您可以將下列 IP 子網指派給北美地區的紐約網站： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果 Bob 通常是在底特律中運作，在紐約辦公室進行訓練，然後開啟他的電腦並聯機到網路上，他的電腦將會取得 IP 位址，並在為紐約所指派的四個範圍中的其中一個，例如172.29.80.103。

> [!CAUTION]
> 在伺服器的網路設定期間指定的 IP 子網必須符合用戶端電腦所提供的格式，才能正確地用於媒體旁路。 商務用 Skype 用戶端會採用其本機 IP 位址，並使用相關聯的子網路遮罩來遮罩 IP 位址。 在判斷與每個用戶端相關的旁路識別碼時，註冊機構會將與每個網路網站相關聯的 IP 子網清單與用戶端提供的子網進行比較，以取得完全相符的專案。 基於這個原因，在伺服器的網路設定期間輸入的子網很重要，而不是虛擬子網。 （如果您部署 [呼叫許可控制]，但無法使用 [媒體旁路]，即使您設定虛擬子網，也能正常使用通話許可控制功能。）例如，如果商務用 Skype 用戶端在 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦上登入，則會要求與子網172.29.81.0 相關聯的旁路 ID。 如果子網是定義為 172.29.0.0/16，雖然用戶端屬於虛擬子網，但註冊機構不會認為這個相符，因為註冊機構特別想要尋找子網172.29.81.0。 因此，系統管理員必須完全按照商務用 Skype 用戶端所提供的子網（在網路設定期間是靜態或動態主機設定通訊協定（DHCP））來輸入子網，這一點很重要。

## <a name="associating-subnets-with-network-sites"></a>將子網與網路網站建立關聯

商業網路中的每個子網都必須與網路網站相關聯（也就是說，每個子網上都需要與地理位置相關聯）。 這個子網的關聯性能讓 [高級企業語音] 功能在地理位置找到端點。 例如，找出端點可讓 CAC 從網路網站傳送即時音訊及視頻資料的流程。

若要將子網與網路網站建立關聯，您可以使用商務用 Skype Server [控制台] 的 [**網路**設定] 區段，或者您可以使用商務用 Skype Server 管理命令介面。 如需相關指示，請參閱在部署檔中[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)，或參閱商務用 Skype Server 管理命令介面檔。

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中規劃通話許可控制](call-admission-control.md)

[在商務用 Skype Server 中規劃緊急服務](emergency-services.md)

[在商務用 Skype 中規劃媒體旁路](media-bypass.md)

