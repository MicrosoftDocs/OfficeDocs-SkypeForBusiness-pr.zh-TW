---
title: 在商務用 Skype Server 中使用內部部署 PSTN 連線來規劃 Office 365 中的電話系統
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: 瞭解使用內部部署 PSTN 連線的 Office 365 (雲端 PBX) 中的手機系統規劃考慮。
ms.openlocfilehash: 1ca12d1680b56612c2e6f3a1785ee615138294ce
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193944"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在商務用 Skype Server 中使用內部部署 PSTN 連線來規劃 Office 365 中的電話系統

瞭解使用內部部署 PSTN 連線的 Office 365 (雲端 PBX) 中的手機系統規劃考慮。

如果您已在內部部署已部署商務用 Skype Server 或 Lync Server 2013, 此內容則是相關的。 若是其他案例, 請參閱[Microsoft 電話方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)。

 使用內部部署 PSTN 連線的 Office 365 中的電話系統, 可讓您為使用者運用電話系統 (雲端 PBX) 功能。 這可協助您進行下列案例:

- 您的部分商務用 Skype 使用者位於內部部署, 而其他人則駐留在商務用 Skype Online 中。 您現在可以針對駐留在商務用 Skype Online 中的使用者啟用 Office 365 功能和功能中的電話系統, 但繼續使用內部部署 PSTN 連線。

- 您有內部部署部署, 而且您想要將部分或所有使用者移至商務用 Skype Online, 但繼續使用內部部署 PSTN 連線。

    > [!IMPORTANT]
    > 若要在使用內部部署 PSTN 連線的 Office 365 中成功啟用電話系統的使用者, 其 SIP 位址必須位於您自己的網域中。 不支援使用 Office 365、onmicrosoft.com 的預設網域。 

若要深入瞭解 Office 365 中的電話系統 (包括授權和方案), 請參閱[商務用 Skype 的 PSTN 通話方案](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。

## <a name="feature-comparison"></a>功能比較

含內部部署 PSTN 連線的雲端 PBX 不會提供與完全內部部署企業語音方案相同的功能集。 為了協助您決定具有內部部署 PSTN 連線的雲端 PBX 是否會為貴組織提供正確的功能集, 請參閱[以下是您使用雲端 pbx 取得](https://go.microsoft.com/fwlink/?LinkId=715517)的功能。

## <a name="benefits-and-planning-considerations"></a>福利與規劃考慮

> [!CAUTION]
> 在移至商務用 Skype Online 之前, 必須先更新 Lync 手機版裝置, 才能使用您的內部部署環境中的最低所需固件。
如果您在更新固件前將使用者從內部部署移至線上, 使用者將無法使用手機連線。 若要修正此問題, 必須將使用者移回內部部署環境, 才能將其手機更新為最低固件。 在將使用者移回您的內部部署環境之前, 請勿嘗試更新到最低固件或硬重設為手機。
如果在裝置不是最小固件時執行硬重設, 則會預設使用 PIN 驗證, 這在商務用 Skype Online 中不受支援。 如需詳細資訊, 請參閱[取得商務用 Skype Online 的電話](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。

透過使用內部部署 PSTN 連線來部署 Office 365 中的電話系統, 您可以透過商務用 Skype Online 以自己的速度將您的使用者移至雲端, 同時保留其內部部署 PSTN 連線能力。 如果您有 PBX, 您會繼續使用它, 為您移至雲端的使用者提供 PSTN 連線能力。 當使用者移至 Office 365 中的商務用 Skype Online 和電話系統之後, 其舊版 PBX 手機將無法運作, 但是他們的電話號碼會傳送到任何適用于電腦或智慧手機的商務用 Skype 用戶端, 以及商務用 Skype 相容的手機已. 移植之後, Office 365 使用者和舊版 PBX 中的電話系統就能正常呼叫對方, 也可以使用其正常電話號碼撥打 PSTN 電話。

您的舊版 PBX (例如話務中心) 可能有自訂功能或主要附加元件。 如果您目前在 Office 365 的電話系統上無法使用自訂功能, 您應該讓那些需要該自訂功能的使用者能夠與舊版 PBX 共同作業, 然後只將不需要存取自訂功能的使用者移植至 Office 365 中的電話系統使用內部部署 PSTN 連線能力。

如需與商務用 Skype Server 2015 直接互動的舊版 Pbx 清單, 請參閱[Microsoft Lync 合格的基礎結構](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway)。 如果您的 PBX 不在此清單中, 您可以使用會話邊界控制器, 在商務用 Skype Online 的 Office 365 中, 將您的 PBX 與電話系統進行連線。

### <a name="network-considerations-for-quality-and-performance"></a>品質與效能的網路考慮

在 Office 365 中使用與內部部署 PSTN 連線的方式部署雲端託管服務 (如手機系統), 您必須牢記下列事項。 在純粹的內部部署商務用 Skype Server 2015 企業語音部署中, 所有的基礎結構和用戶端都在企業自己的網路上。 此網路的品質和效能對於高品質的音訊和影片而言, 這是在企業員工的直接控制之下。 在具備內部部署 PSTN 連線的 Office 365 中, 有三個網路參與, 但客戶只負責其中兩個網路, 但只有其中一個企業員工可以直接控制:

- **Microsoft 的全域媒體傳遞網路**Microsoft 的全域雲端網路和基礎結構。 Office 365 伺服器中的 office 365 和電話系統, 以及流經此網路的流量。

- **企業/雲端 PSTN 互連**這是將企業連接至 Office 365 雲端的網路。 這不一定與您的一般網際網路連線相同。

- **貴企業自己的網路**即時媒體的品質非常依賴您自己的網路: 尤其是 WiFi 網路, 以及用來達到 Office 365 雲端的互連品質。

> [!NOTE]
> 如需調整商務用 Skype Online 效能的詳細資訊, 請參閱[微調商務用 Skype online 的效能](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US)。 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>在 Office 365 中使用電話系統與內部部署 PSTN 連線的先決條件

在您可以使用內部部署 PSTN 連線來設定 Office 365 中的電話系統, 並將使用者移至商務用 Skype Online 前, 您必須確認您有下列先決條件:

 **內部部署伺服器版本。** 您內部部署部署中的伺服器版本必須列在下表中, 以支援使用內部部署 PSTN 連線的 Office 365 中的電話系統。


| **伺服器角色**                                       | **支援的版本\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| 同盟邊緣\*\*  <br/>                            | 商務用 Skype Server 2015  <br/>                                                                              |
| 下一個躍點同盟路由內部池伺服器  <br/> | 商務用 Skype Server 2015, 2016 年3月累計更新6.0.9319.235 或更新版本 (前端或控制器)  <br/> |
| 前端使用者伺服器  <br/>                          | 商務用 Skype Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edge 伺服器  <br/>                                    | 商務用 Skype Server 2015  <br/>                                                                              |
| 中繼伺服器  <br/>                               | 商務用 Skype Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*支援的最低版本如下:

- 商務用 Skype Server 2015, 2016 年3月累計更新6.0.9319.235

- Lync Server 2013 年 7 2015 月累計更新5.0.8308.920

\*\*所有受支援的 SIP 網域的同盟路由都必須透過運行3月2016或較高累計更新的商務用 Skype Server 2015 Edge 伺服器進行路由。 如果使用者池是在 Lync Server 2013 上, 則該外部池流量會保留在 Lync Server 2013 Edge 伺服器上。 

此外, 您必須確保下列各項:

- 針對內部**部署使用者設定並測試內部部署的企業語音**這包括 PSTN 連通性元件。 如需詳細資訊, 請參閱下列主題: 如果您使用的是商務用 Skype Server 2015, 請參閱[在商務用 Skype server 2015 規劃企業版語音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md), 以及[在商務用 skype Server 2015 中部署企業版語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。

    如果您使用的是 Lync Server 2013, 請參閱[在 Lync server 2013 中規劃企業語音](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx), 並[在 lync Server 2013 中部署企業版語音](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx)。

- **Active Directory 同步**處理您必須使用 Azure AD Connect 設定 Active Directory 同步處理。 如需詳細資訊, 請參閱[管理 AZURE AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)。

    > [!NOTE]
    > 您使用的 AAD 連接版本必須是版本1.0.9125.0 或更新版本。 如果您使用的是舊版的 AAD Connect 工具或 DirSync, 請升級至支援的版本。 您可以升級您目前的安裝, 並維護您在環境中定義的任何自訂規則。 

- **設定您的混合式部署**不論您的所有商務用 Skype 使用者目前都是在線上或內部部署中, 或是如果您目前已有混合式功能, 您必須完成設定商務用 Skype Server 或 Lync Server 2013 的混合式部署的步驟, 如部署混合式中所述。 [商務用 Skype 伺服器與 Office 365 之間的](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)連線。 如需混合式部署的詳細背景資訊, 請參閱[規劃商務用 Skype Server 與 Office 365 之間的混合式連接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 

    如果您使用的是 Lync Server 2013, 請參閱[Lync server 2013 混合](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx)式。

- **採用Active Directory 同盟服務 (AD FS)。** 我們建議您部署 AD FS 以支援單一登入。 如需詳細資訊, 請參閱[Active Directory Federation Services (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx)。

如需在 Office 365 中部署電話系統的相關資訊, 請參閱在[商務用 Skype Server 的內部部署 PSTN 連線中, 在 office 365 中啟用手機系統的使用者](enable-users-for-phone-system.md)。


