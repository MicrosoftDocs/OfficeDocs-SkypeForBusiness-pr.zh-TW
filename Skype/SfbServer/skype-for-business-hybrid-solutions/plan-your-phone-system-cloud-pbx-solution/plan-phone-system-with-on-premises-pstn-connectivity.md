---
title: 在商務用 Skype Server 中規劃含有內部部署 PSTN 連線功能的電話系統
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 深入瞭解使用內部部署 PSTN 連線的電話系統 (雲端 PBX) 規劃考慮。
ms.openlocfilehash: e0caed5560e7b7609adbfccf79e4ef63ee4eae09
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110539"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃含有內部部署 PSTN 連線功能的電話系統

> [!Important]
> 在2021年7月31日之後，商務用 Skype Online 將會停用，在此之後將無法再存取服務。  此外，您的內部部署環境之間的 PSTN 連線，不論是透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype Online，都將不再支援。  瞭解如何使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。

深入瞭解使用內部部署 PSTN 連線的電話系統 (雲端 PBX) 規劃考慮。

如果您已在內部部署中部署商務用 Skype Server 或 Lync Server 2013，則此內容是相關的。 如需其他案例，請參閱 [Microsoft 電話語音解決方案](../../../SfbHybrid/hybrid/msft-telephony-solutions.md)。

 使用內部部署 PSTN 連線的電話系統可讓您為使用者利用電話系統 (雲端 PBX) 功能。 這可協助您進行下列案例：

- 您的部分商務用 Skype 使用者位於內部部署和其他位於商務用 Skype Online 中。 您現在可以為位於商務用 Skype Online 中的使用者啟用電話系統功能和功能，但繼續使用內部部署 PSTN 連線。

- 您有內部部署，且想要將部分或所有使用者移至商務用 Skype Online，但繼續使用內部部署 PSTN 連線。

    > [!IMPORTANT]
    > 若要使用內部部署 PSTN 連線成功啟用電話系統的使用者，他們的 SIP 位址必須位於您自己的網域中。 不支援使用 Microsoft 365 或 Office 365，onmicrosoft.com 的預設網域。 

若要深入瞭解電話系統，包括授權與計畫，請參閱 [適用于商務用 Skype 的 PSTN 通話方案](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>功能比較

使用內部部署 PSTN 連線的雲端 PBX 不會提供與完全內部部署企業語音解決方案相同的功能集。 為了協助您決定具有內部部署 PSTN 連線的雲端 PBX 是否會為您的組織提供正確的功能集，請參閱 [以下是您使用雲端 PBX 取得](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)的功能。

## <a name="benefits-and-planning-considerations"></a>優點和規劃考慮

> [!CAUTION]
> Lync Phone Edition 裝置必須更新為您的內部部署環境中的最小必要固件，才能移至商務用 Skype Online。
如果您在更新固件之前，將使用者從內部部署移至線上，使用者將無法使用電話進行連線。 若要修正此問題，必須將使用者移回內部部署環境，讓他們的手機更新至最低的固件。 在將使用者移回您的內部部署環境之前，請勿嘗試更新至最低固件或硬重設電話。
如果在裝置不是最低固件時執行硬重設，則預設會使用 PIN 碼驗證，這在商務用 Skype Online 中不受支援。 如需詳細資訊，請參閱 [取得商務用 Skype Online 的電話](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

透過部署具有內部部署 PSTN 連線的電話系統，您可以根據自己的節奏，透過商務用 Skype Online 將使用者移至雲端，同時保留其內部部署 PSTN 連線能力。 如果您有 PBX，您可以繼續使用它，為您移至雲端的使用者提供 PSTN 連線能力。 一旦使用者移至商務用 Skype Online 和電話系統，其舊版 PBX 電話就無法再運作，但他們的電話號碼會路由傳送至任何電腦或智慧型電話的商務用 Skype 用戶端，以及商務用 Skype 相容的服務台電話。 一旦傳送後，電話系統使用者和舊版 PBX 使用者就能以一般的電話號碼撥打對方通話，並撥打/接收 PSTN 電話。

您可以對舊版 PBX 使用自訂功能或主要附加元件，例如通話中心。 若自訂功能目前在電話系統上無法使用，您應該將需要該自訂功能的使用者留給舊版 PBX 使用，而且只需將不需要存取自訂功能的使用者的埠與內部部署 PSTN 連接。

如需與商務用 Skype Server 2015 直接互動的舊版 PBXs 清單，請參閱  [Microsoft Lync 的基礎結構限定](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 如果您的 PBX 不在此清單上，您可以使用會話邊界控制器，在商務用 Skype Online 中使用電話系統來連接 PBX。

### <a name="network-considerations-for-quality-and-performance"></a>品質和效能的網路考慮

當您使用內部部署 PSTN 連線部署雲端裝載服務（例如電話系統）時，您必須記住下列事項。 在單純的內部部署商務用 Skype Server 2015 Enterprise Voice 部署中，所有基礎結構和用戶端都位於企業自身的網路上。 這項網路的品質和效能是高品質音訊和影片的關鍵，都是企業人員的直接控制。 使用具有內部部署 PSTN 連線的電話系統，有三個網路，客戶負責的兩個網路，但只有其中一個企業人員可以直接控制下列專案：

- **Microsoft 的全域媒體傳遞網路** Microsoft 的全球雲端網路和基礎結構。 跨越此網路的電話系統伺服器及流量。

- **Enterprise/雲端 PSTN 互連** 這是將企業連接至雲端的網路。 這不一定與一般網際網路連線相同。

- **企業自身的網路** 即時媒體的品質很大取決於您自己的網路：尤其是 WiFi 網路，以及用來抵達雲端的互連品質。

> [!NOTE]
> 如需在商務用 Skype Online 中調整效能的詳細資訊，請參閱 [調整商務用 Skype online 效能](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>使用具有內部部署 PSTN 連線的電話系統的必要條件

您必須先確認您已具備下列必要條件，才能設定具有內部部署 PSTN 連線的電話系統並將使用者移至商務用 Skype Online。

 **內部部署伺服器的版本。** 您的內部部署部署中的伺服器版本必須列在下表中，以支援具有內部部署 PSTN 連線的電話系統。


| **伺服器角色**                                       | **支援的版本\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 同盟 Edge\*\*  <br/>                            | 商務用 Skype Server 2015  <br/>                                                                              |
| 下一個躍點同盟路由內部集區伺服器  <br/> | 商務用 Skype Server 2015，三月份2016累計更新6.0.9319.235 或更新版本 (前端或 Director)   <br/> |
| 前端使用者伺服器  <br/>                          | 商務用 Skype Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge Server  <br/>                                    | 商務用 Skype Server 2015  <br/>                                                                              |
| 中繼伺服器  <br/>                               | 商務用 Skype Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*支援的最低版本包括：

- 商務用 Skype Server 2015，2016年3月累計更新6.0.9319.235

- Lync Server 2013 年 7 2015 月累積更新5.0.8308.920

\*\*所有支援的 SIP 網域的同盟路由，都必須透過執行三月份2016或更高累計更新的商務用 Skype Server 2015 Edge Server 進行路由傳送。 如果使用者集區位於 Lync Server 2013，該外部集區流量仍會保留在 Lync Server 2013 Edge Server 上。 

此外，您必須確定下列各項：

- 內部部署的 **Enterprise Voice 為內部部署使用者設定並測試** 這包括 PSTN 連接元件。 如需詳細資訊，請參閱下列主題：如果您使用商務用 Skype Server 2015，請參閱在商務用 skype [server 2015 中規劃 Enterprise voice](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) ，以及 [在商務用 skype Server 2015 中部署企業語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。

    如果您使用的是 Lync Server 2013，請參閱在 lync server [2013 中規劃 Enterprise voice](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) ，並 [在 lync Server 2013 中部署企業語音](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice)。

- **Active Directory 同步** 處理您必須使用 Azure AD Connect 設定 Active Directory 同步處理。 如需詳細資訊，請參閱 [管理 AZURE AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)。

    > [!NOTE]
    > 您使用的 AAD 連線版本必須是版本1.0.9125.0 或更新版本。 如果您使用的是舊版本的 AAD Connect tools 或 DirSync，請升級至支援的版本。 您可以升級目前的安裝，並維護您在環境中所定義的任何自訂規則。 

- **設定混合部署** 不論您的所有商務用 Skype 使用者目前是線上或內部部署的，還是如果您目前有混合式，您必須完成步驟以設定商務用 skype server 或 Lync Server 2013 的混合式部署，如在 [商務用 Skype server 與 Office 365 之間部署混合](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)式連線的說明所述。 如需混合式部署的更多背景資訊，請參閱 [規劃商務用 Skype Server 與 Office 365 之間的混合](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)式連線。 

    如果您使用的是 Lync Server 2013，請參閱 [Lync server 2013 混合](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)式。

- **(建議) Active Directory Federation Services (AD FS) 。** 建議您部署 AD FS 以支援單一登入。 如需詳細資訊，請參閱 [Active Directory Federation Services (AD FS) ](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))。

如需部署電話系統的相關資訊，請參閱 [在商務用 Skype Server 中使用內部部署 PSTN 連線啟用使用者的電話系統](enable-users-for-phone-system.md)。