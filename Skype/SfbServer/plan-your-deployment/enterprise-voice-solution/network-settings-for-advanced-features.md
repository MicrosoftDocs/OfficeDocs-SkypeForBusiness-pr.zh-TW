---
title: 商務用 Skype Server 中的高級企業語音功能的網路設定
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: 深入瞭解網路地區、網路網站和 IP 子網。 所有這些都必須設定為在商務用 Skype 中部署媒體旁路的計畫、在商務用 Skype Server) 中規劃通話許可控制，或在商務用 Skype Server 企業語音的商務用 Skype Server 中規劃緊急服務。
ms.openlocfilehash: 77472a77f26139f7a15f0a3820e6fb90a798a5b7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391875"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>商務用 Skype Server 中的高級企業語音功能的網路設定

深入瞭解網路地區、網路網站和 IP 子網。 所有這些都必須設定為[在商務用 Skype 中部署媒體旁路的計畫](media-bypass.md)、在[商務用 Skype Server 中規劃通話許可控制](call-admission-control.md)，或在[商務用 Skype Server 中規劃緊急服務](emergency-services.md)商務用 Skype Server企業語音。

商務用 Skype Server 有三個高級企業語音功能：[在商務用 Skype Server 中規劃通話許可控制](call-admission-control.md)、在[商務用 Skype Server 中規劃緊急服務](emergency-services.md)，以及[在商務用 Skype 中規劃媒體旁路](media-bypass.md)。 這些功能會共用網路地區、網路網站及商務用 Skype Server 拓撲中每個子網與網路網站關聯的特定設定需求。

本主題概述所有三種高級企業語音功能的常見設定需求。

## <a name="network-regions"></a>網路地區

網路地區是一種網路中樞或網路骨幹，只有在通話許可控制 (CAC)、E9-1-1 和媒體旁路的組態中才會使用。

> [!NOTE]
> 網路地區與商務用 Skype Server 電話撥入式會議地區不同，後者與一或多個商務用 Skype Server 撥號對應表建立電話撥入式會議存取號碼的要求。 如需電話撥入式會議地區的詳細資訊，請參閱 [規劃 Dial-In 會議](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements)。

CAC 需要每個網路地區都有相關聯的商務用 Skype Server 中央網站，該網站會管理地區內的媒體流量 (也就是說，它會根據您設定的原則進行決策，關於是否可以) 建立即時音訊或視頻會話。 商務用 Skype Server 中央網站不代表地理位置，而是設定為集區或集區集區的邏輯群組。

若要設定網路地區，您可以使用商務用 Skype Server 控制台的 [**網路** 設定] 區段中的 [**區域**] 索引標籤，或執行 **New-CsNetworkRegion** 或 **Set-CsNetworkRegion** 商務用 Skype Server 管理命令介面 Cmdlet。 如需相關指示，請參閱部署檔中的[商務用 Skype 部署網路地區、網站和子網](../../deploy/deploy-enterprise-voice/deploy-network.md)，或是參考商務用 Skype Server 管理命令介面檔。

所有三個高級企業語音功能都會共用相同的網路地區定義。 如果您已為其中一項功能建立網路地區，即無須再為其他功能建立新的網路地區。 但您可能需要修改現有的網路地區定義，以套用功能特有的設定。 例如，如果您為 E9-1-1 (不需要有相關聯的中央網站) 建立網路地區後，又部署了通話許可控制，則必須修改每個網路地區定義以指定中央網站。

若要將商務用 Skype Server 的中央網站與網路地區產生關聯，您可以使用商務用 Skype Server 控制台] 的 [**網路** 設定] 區段，或執行 **New-CsNetworkRegion** 或 **Set-CsNetworkRegion** Cmdlet 來指定中央網站名稱。 如需相關指示，請參閱部署檔中的[商務用 Skype 部署網路地區、網站和子網](../../deploy/deploy-enterprise-voice/deploy-network.md)，或是參考商務用 Skype Server 管理命令介面檔。

## <a name="network-sites"></a>網站

網路網站代表地理位置，例如分公司、地區辦事處或總公司。每個網路網站都必須與某個網路地區相關聯。

> [!NOTE]
> 僅限「高級企業語音功能使用網路網站。 它們不同于您在商務用 Skype Server 拓撲中設定的分支網站。

若要設定網路網站，並將其與網路地區產生關聯，您可以使用商務用 Skype Server 控制台的 [**網路** 設定] 區段，或執行商務用 Skype Server 管理命令介面 **New-CsNetworkSite** 或 **Set-CsNetworkSite** Cmdlet。 如需詳細資訊，請參閱部署檔中的[建立或修改網站](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)，或參考商務用 Skype Server 管理命令介面檔。

## <a name="identify-ip-subnets"></a>識別 IP 子網路

對於每一個網站，您需要和網路管理員一同決定要指派給每一個網站的 IP 子網路。如果您的網路管理員已經整理好各個網路地區與網站的 IP 子網路，您的工作將會大幅簡化。

例如，可以將指派以下 IP 子網路給北美洲區域內的紐約網站：172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. 假設平常在 Detroit 工作的 Bob 要到 New York 分公司受訓。當他開啟自己的電腦並連線至網路時，他的電腦會取得分配給紐約的四個範圍內的其中一個 IP 位址，例如，172.29.80.103。

> [!CAUTION]
> 在伺服器上的網路設定期間指定的 IP 子網必須符合用戶端電腦所提供的格式，才能正確用於媒體旁路。 商務用 Skype 用戶端採用其本機 IP 位址，並以關聯的子網路遮罩遮罩 IP 位址。 決定與每一位用戶端相關聯的旁路識別碼時，註冊機構會比較與用戶端所提供之子網相關聯的 IP 子網清單，以取得完全相符的專案。 因此，在伺服器上的網路設定期間輸入的子網，必須是實際的子網，而不是虛擬子網，這一點很重要。  (如果您部署通話許可控制，但未使用媒體旁路，則即使您設定虛擬子網，通話許可控制也會正常運作。 ) 例如，如果商務用 Skype 用戶端使用具有 ip 子網路遮罩255.255.255.0 的 ip 位址來登入，則會要求與子網172.29.81.0 相關聯的旁路識別碼。 如果子網路定義為 172.29.0.0/16，則儘管用戶端屬於虛擬子網路，登錄器仍舊不會將其視為完全相符，因為登錄器所尋找的是真正的子網路 172.29.81.0。 因此，管理員必須在網路設定（靜態或透過動態主機設定通訊協定 (DHCP) ）中，以商務用 Skype 用戶端 (所提供的方式輸入子網，這一點很重要。 ) 

## <a name="associating-subnets-with-network-sites"></a>建立子網路與網路網站的關聯

企業網路中的每個子網路都必須與某個網路網站相關聯 (亦即，每個子網路都必須與某個地理位置相關聯)。 這種子網的關聯性可讓 advanced 企業語音功能在地理位置找到端點。 例如，找出端點位置後，CAC 可以調節進出該網路網站的即時音訊與視訊資料流量。

若要將子網與網站產生關聯，您可以使用商務用 Skype Server 控制台的 [**網路** 設定] 區段，也可以使用商務用 Skype Server 管理命令介面。 如需相關指示，請參閱在部署檔中[建立子網與網站的關聯](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)，或是參考商務用 Skype Server 管理命令介面檔。

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中規劃通話許可控制](call-admission-control.md)

[在商務用 Skype Server 中規劃緊急服務](emergency-services.md)

[在商務用 Skype 中規劃媒體旁路](media-bypass.md)