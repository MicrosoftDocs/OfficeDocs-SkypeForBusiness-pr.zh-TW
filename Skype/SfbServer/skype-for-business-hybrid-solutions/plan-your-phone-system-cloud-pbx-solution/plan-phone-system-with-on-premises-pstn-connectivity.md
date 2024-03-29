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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 瞭解電話系統 (雲端 PBX) 搭配內部部署 PSTN 連線的規劃考慮。
ms.openlocfilehash: a3c01ed32cb2654ea10773f53c4148262e3ee6c5
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562775"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃含有內部部署 PSTN 連線功能的電話系統

> [!Important]
> 已不再支援內部部署環境（不論是商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype 線上）上的商務用 Skype 線上，都已2021淘汰。  瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線至 Teams。

瞭解電話系統 (雲端 PBX) 搭配內部部署 PSTN 連線的規劃考慮。

如果您已在內部部署中部署商務用 Skype Server 或 Lync Server 2013，則此內容是相關的。 如需其他案例，請參閱 [Microsoft 電話語音解決方案](/microsoftteams/cloud-voice-landing-page)。

 使用內部部署 PSTN 連線電話系統可讓您利用電話系統 (雲端 PBX) 使用者功能。 這可協助您進行下列案例：

- 您的部分商務用 Skype 使用者位於內部部署，而其他使用者位於商務用 Skype 線上。 您現在可以為位於商務用 Skype Online 中的使用者啟用電話系統功能和功能，但會繼續使用內部部署 PSTN 連線。

- 您有內部部署，且想要將部分或所有使用者移至商務用 Skype 線上，但繼續使用內部部署 PSTN 連線。

    > [!IMPORTANT]
    > 若要使用內部部署 PSTN 連線順利為使用者啟用電話系統，其 SIP 位址必須位於您自己的網域中。 不支援使用 Microsoft 365 或 Office 365，onmicrosoft.com 的預設網域。 

若要深入瞭解電話系統，包括授權與計畫，請參閱[商務用 Skype 的 PSTN 通話方案](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>功能比較

具有內部部署 PSTN 連線的雲端 PBX 不會提供與完整內部部署企業語音解決方案相同的功能集。 為了協助您決定具有內部部署 PSTN 連線的雲端 PBX 是否會為您的組織提供正確的功能集，請參閱 [以下是您使用雲端 PBX 取得](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)的功能。

## <a name="benefits-and-planning-considerations"></a>優點和規劃考慮

> [!CAUTION]
> 在您移動至商務用 Skype 線上之前，必須更新您的內部部署環境中的最小必要固件（Lync 電話 Edition 裝置）。
如果您在更新固件之前，將使用者從內部部署移至線上，使用者將無法使用電話進行連線。 若要修正此問題，必須將使用者移回內部部署環境，讓他們的手機更新至最低的固件。 在將使用者移回您的內部部署環境之前，請勿嘗試更新至最低固件或硬重設電話。
如果在裝置不是最低固件時執行硬重設，則預設會使用 PIN 驗證，這在商務用 Skype Online 中不受支援。 如需詳細資訊，請參閱[取得線上商務用 Skype 的電話](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

透過使用內部部署 pstn 連線部署電話系統，您可以在自己的節奏上透過商務用 Skype 線上，將使用者移至雲端，同時保留其內部部署 pstn 連線能力。 如果您有 PBX，您可以繼續使用它，為您移至雲端的使用者提供 PSTN 連線能力。 一旦使用者移至商務用 Skype 線上和電話系統，其舊版 PBX 電話將無法再運作，但他們的電話號碼會路由傳送至電腦或智慧型電話的任何商務用 Skype 用戶端，以及商務用 Skype 相容的桌面電話。 一旦傳送後，電話系統使用者和舊版 PBX 使用者可以以一般方式呼叫對方，以及撥打/接收 PSTN 來電使用其正常的電話號碼。

您可以對舊版 PBX 使用自訂功能或主要附加元件，例如通話中心。 如果電話系統上目前不提供自訂功能，您應該將需要該自訂功能的使用者留給舊版 PBX 使用，並只將不需要存取自訂功能的使用者連接至與內部部署 PSTN 連線電話系統。

如需直接與商務用 Skype Server 2015 互動的舊版 PBXs 清單，請參閱[Microsoft Lync 的基礎結構限定](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 如果您的 pbx 不在此清單上，您可以使用會話邊界控制器，將 PBX 與電話系統商務用 Skype 線上。

### <a name="network-considerations-for-quality-and-performance"></a>品質和效能的網路考慮

使用內部部署 PSTN 連線部署雲端裝載服務（如電話系統）時，您必須記住下列事項。 在單純的內部部署商務用 Skype Server 2015 企業語音部署中，所有基礎結構和用戶端都位於企業本身的網路上。 這項網路的品質和效能是高品質音訊和影片的關鍵，都是企業人員的直接控制。 使用具有內部部署 PSTN 連線的電話系統，有三個網路，客戶只負責其中兩個網路，但只有其中一個企業人員可以直接控制下列專案：

- **Microsoft 的全域媒體傳遞網路** Microsoft 的全球雲端網路和基礎結構。 電話系統伺服器及流量流經此網路。

- **Enterprise/Cloud PSTN 互連** 這是將企業連接至雲端的網路。 這不一定與一般網際網路連線相同。

- **企業自身的網路** 即時媒體的品質很大取決於您自己的網路：尤其是 WiFi 網路，以及用來抵達雲端的互連品質。

> [!NOTE]
> 如需在線上商務用 Skype 調整效能的詳細資訊，請參閱[微調商務用 Skype 線上效能](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>搭配內部部署 PSTN 連線使用電話系統的必要條件

您必須先確認已具備下列必要條件，才能使用內部部署 PSTN 連線設定電話系統，並將使用者移至商務用 Skype 線上。

 **內部部署伺服器的版本。** 在內部部署部署中的伺服器版本必須列在下表中，以支援與內部部署 PSTN 連線的電話系統。


| **伺服器角色**                                       | **支援的版本\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 同盟 Edge\*\*  <br/>                            | 商務用 Skype Server 2015  <br/>                                                                              |
| 下一個躍點同盟路由內部集區伺服器  <br/> | 商務用 Skype Server 2015，3月2016累積更新6.0.9319.235 或更新版本 (前端或 Director)   <br/> |
| 前端使用者伺服器  <br/>                          | 商務用 Skype Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge Server  <br/>                                    | 商務用 Skype Server 2015  <br/>                                                                              |
| 中繼伺服器  <br/>                               | 商務用 Skype Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*支援的最低版本包括：

- 商務用 Skype Server 2015，6.0.9319.235 2016 年3月累計更新

- Lync Server 2013 年 7 2015 月累積更新5.0.8308.920

\*\*所有支援的 SIP 網域的同盟路由都必須透過執行3月2016或更高累積更新的商務用 Skype Server 2015 Edge Server 進行路由傳送。 如果使用者集區位於 Lync Server 2013，該外部集區流量仍會保留在 Lync Server 2013 Edge Server 上。 

此外，您必須確定下列各項：

- **內部部署使用者企業語音已設定並測試內部部署使用者**，這包括 PSTN 連接元件。 如需詳細資訊，請參閱下列主題如果使用商務用 Skype Server 2015，請參閱[Plan for 企業語音 in 商務用 Skype Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) ，並[在商務用 Skype Server 2015 中部署企業語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。

    如果您使用的是 lync server 2013，請參閱在 lync server [2013 中規劃企業語音](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice)和[在 lync server 2013 中部署企業語音](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice)。

- **Active Directory 同步** 處理您必須使用 Azure AD 連線設定 Active Directory 同步處理。 如需詳細資訊，請參閱[Azure AD 連線](/azure/active-directory/hybrid/how-to-connect-install-custom)。

    > [!NOTE]
    > 您使用的 AAD 連線版本必須是版本1.0.9125.0 或更新版本。 如果您使用舊版 AAD 連線工具或 DirSync，請升級至支援的版本。 您可以升級目前的安裝，並維護您在環境中所定義的任何自訂規則。 

- **設定混合部署** 不論您的所有商務用 Skype 使用者目前是線上或內部部署的伺服器，或是目前是否混合使用，您必須完成設定商務用 Skype Server 或 Lync Server 2013 混合式部署的步驟，如 [部署商務用 Skype Server 和 Office 365 間的混合式連線所述。](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). 如需混合式部署的更多背景資訊，請參閱[規劃商務用 Skype Server 和 Office 365 之間的混合](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)式連線。 

    如果您使用的是 Lync Server 2013，請參閱 [Lync server 2013 混合](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)式。

- **(建議) Active Directory Federation Services (AD FS) 。** 建議您部署 AD FS 以支援單一登入。 如需詳細資訊，請參閱 [Active Directory Federation Services (AD FS) ](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))。

如需部署電話系統的相關資訊，請參閱[商務用 Skype Server 中的內部部署 PSTN 連線電話系統啟用使用者](enable-users-for-phone-system.md)。
