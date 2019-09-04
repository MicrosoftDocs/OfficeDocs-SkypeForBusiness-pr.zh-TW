---
title: 規劃混合式連接 |商務用 Skype Server 2019 Office 365 整合
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 規劃在商務用 Skype Server 與商務用 Skype Online 或團隊之間實現混合式連線的考慮。
ms.openlocfilehash: 65e0f19e536cb2ec9b92fc73a1abb938be3b3c7c
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715826"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>規劃商務用 Skype Server 與 Office 365 之間的混合式連接

## <a name="overview"></a>概觀

請閱讀本主題, 瞭解如何規劃商務用 Skype Server 與團隊或商務用 Skype Online 之間的混合式連線性。 設定混合式連接是將內部部署環境移至雲端的第一個步驟。

如果您有使用團隊的內部部署商務用 Skype 使用者 (並排), 這些使用者就無法與來自團隊用戶端的商務用 Skype 使用者進行交互操作, 也無法與同盟組織中的使用者通訊。團隊用戶端。 若要在團隊中取得這項功能, 必須將這些使用者從商務用 Skype 內部部署移至雲端, 這需要設定商務用 Skype 混合模式。 此外, 若要獲得最佳體驗, 這些使用者應該是 [僅限團隊] 模式, 可確保使用者團隊用戶端中所有使用者的來電與聊天。

您也必須先設定混合式連接, 並將所有使用者移至雲端, 才能讓您的內部部署商務用 Skype 部署停止。  設定混合式連線性後, 您可以根據排程和業務需求選擇將使用者移至雲端。 借助直接路由, 您可以在移動到雲端和完成遷移之後, 利用內部部署的語音結構。

本主題描述您將在現有內部部署商務用 Skype Server 部署與團隊或商務用 Skype Online 之間設定混合式連線性所需的基礎結構和系統需求。

在您已閱讀本主題並準備好設定混合式連線性之後, 請參閱在[商務用 Skype Server 和 Office 365 之間設定混合式連線性](configure-hybrid-connectivity.md)。 [設定] 主題提供在您的內部部署與團隊或商務用 Skype Online 之間設定混合式連線性的逐步指導方針。

## <a name="about-shared-sip-address-space-functionality"></a>關於共用的 SIP 位址空間功能

<a name="BKMK_Overview"> </a>

 在商務用 Skype Server 與團隊或商務用 Skype Online 之間設定混合式連接, 您可以讓一些使用者駐留在內部部署, 而某些使用者會駐留在線上。

此類型的設定依賴于共用的 SIP 位址空間功能, 有時也稱為「分割網域」-這是網域的使用者 (例如 contoso.com), 是在內部部署與團隊或商務用 Skype 上使用商務用 Skype Server 進行分割[線上], 如下圖所示:

![SfB 混合式連接-分割網域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

已設定共用的 SIP 位址空間:

- Azure Active Directory Connect 是用來將您的內部部署目錄與 Office 365 同步處理。
- 內部部署的使用者會與內部部署的商務用 Skype 伺服器互動。
- 以線上為宿主的使用者可以與商務用 Skype Online 或團隊服務互動。
- 這兩個環境中的使用者都可以彼此通訊。
- 內部部署的 Active Directory 是權威性的。 所有使用者都應該先在內部部署 Active Directory 中建立, 然後同步處理到 Azure AD。 即使您想要讓使用者以線上方式駐留, 您必須先在內部部署環境中建立使用者, 然後將使用者移至 [線上], 以確保使用者可透過內部部署使用者發現使用者。

使用者必須獲指派商務用 Skype Online (方案 2) 授權, 才能在線上移動使用者。 如果使用者使用的是小組, 也必須指派團隊授權 (且商務用 Skype 授權必須保持啟用)。 如果您的使用者想要利用其他線上功能 (例如音訊會議或電話系統), 您必須在 Office 365 中指派適當的授權。

## <a name="infrastructure-requirements"></a>基礎結構需求

<a name="BKMK_Infrastructure"> </a>

若要在您的內部部署環境與 Office 365 通訊服務之間實現混合式連接, 您必須符合下列基礎結構需求:

- 部署在支援的拓撲中的商務用 Skype Server 或 Lync Server 的內部部署。 請參閱本主題中的[拓撲需求](plan-hybrid-connectivity.md#BKMK_Topology)。
- 已啟用商務用 Skype Online 的 Microsoft Office 365 租使用者。
    > [!NOTE]
    > 您只能使用單一租使用者進行混合式設定與您的內部部署。
- Azure Active Directory Connect 可將您的內部部署目錄與 Office 365 同步處理。 如需詳細資訊, 請參閱[AZURE AD Connect: 帳戶和許可權](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。
- 商務用 Skype Server 管理工具。  必須有這些專案, 才能將使用者從內部部署移至雲端。 這些工具必須安裝在可存取內部部署和網際網路的伺服器上。
- 線上管理工具。  您可以使用團隊系統管理中心或 Windows PowerShell 來管理團隊及商務用 Skype Online。 若要使用 PowerShell 來管理團隊或商務用 Skype Online, 請下載並安裝商務用 Skype Online 連接器。
- 必須啟用共用的 SIP 位址空間, 而且您的內部部署部署必須設定為使用 Office 365 做為主機服務提供者。 如需設定混合式連線性所需步驟的詳細資訊, 請參閱[設定混合式連線性](configure-hybrid-connectivity.md)。

設定混合式連線性之後, 您可以將使用者移至團隊或商務用 Skype Online。 如需詳細資訊, 請參閱[將使用者從內部部署移至團隊](move-users-from-on-premises-to-teams.md), 以及[將使用者從內部部署移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。

## <a name="server-version-requirements"></a>伺服器版本需求

<a name="BKMK_Topology"> </a>

若要設定與**團隊或商務用 Skype Online**混合式部署, 您必須具備下列其中一個受支援的拓撲:

- 商務用 Skype Server 2019 部署與所有執行商務用 Skype Server 2019 的伺服器。
- 商務用 Skype Server 2015 部署與所有執行商務用 Skype Server 2015 的伺服器。
- Lync Server 2013 部署與所有執行 Lync Server 2013 的伺服器。  不過, 如果需要混合式語音連接, 您必須使用混合版本拓撲, 如下所述。
- 最多兩個不同伺服器版本的部署, 如下所示:
  - 商務用 skype Server 2015 和商務用 Skype Server 2019
  - Lync Server 2013 和商務用 Skype Server 2019
  - Lync Server 2013 和商務用 Skype Server 2015

*如果在任何拓撲中都需要混合式語音*, 則指定為同盟邊緣的邊緣伺服器以及與 SIP 同盟關聯的池都必須執行商務用 Skype 2015 或更新版本。 使用者可以保留在 Lync 2013 池 (如果有的話)。 如需詳細資訊, 請參閱[在商務用 Skype Server 中使用 PSTN 連線規劃電話系統](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。

下列包括 Lync Server 2010 的拓撲支援在立即訊息與會議的**商務用 Skype Online 中使用**。  **混合式語音和團隊不支援包含 Lync Server 2010**的拓撲。

- 混合式 Lync Server 2010 和商務用 Skype Server 2015 部署
- 混合式 Lync Server 2010 和 Lync Server 2013 部署
- Lync Server 2010 部署, 其中所有執行 Lync Server 2010 的伺服器都有最新的累計更新。

同盟邊緣伺服器與同盟 Edge 伺服器的下一個躍點伺服器必須執行 Lync Server 2010, 並提供最新的累加更新。 商務用 Skype Server 2015 或 Lync Server 2013 系統管理工具必須安裝在至少一個伺服器或管理工作站上。

## <a name="multi-forest-support"></a>多林支援

<a name="BKMK_MultiForest"> </a>

Microsoft 支援下列多種多目錄林混合式案例:

- **資源林拓撲。** 在這種拓撲中, 有一個目錄林主持商務用 Skype Server (資原始目錄林), 而且有一個或多個其他目錄林主持帳戶身分識別, 而您可以在資原始目錄林中存取商務用 Skype 伺服器。 一般來說, 如果符合下列需求, 使用者就可以在其他林中存取商務用 Skype 的功能:
  - 使用者會正確地同步處理到主持商務用 Skype 的林中。 在混合式設定中, 這表示使用者必須以停用的使用者物件進行同步處理。
  - 主持商務用 Skype 的目錄林必須信任包含使用者的目錄林。
    如需有關資原始目錄林混合案例的詳細資料, 請參閱針對[混合式商務用 Skype 部署資源林拓撲](configure-a-multi-forest-environment-for-hybrid.md)。
- **多個目錄林中多個商務用 Skype Server 部署。** 這項設定可能是合併與收購案例的結果, 也可能是在更複雜的企業中產生的。  只要符合下列主要需求, 就能將所有使用者從內部部署到雲端在單一的 Office 365 租使用者中進行整合:

  - 最多隻能有一個 Office 365 租使用者。 不支援在多個 Office 365 租使用者的案例中整合。
  - 在任何指定時間, 只有一個內部部署的商務用 Skype 目錄林可以混合模式 (共用的 SIP 位址空間)。 所有其他內部部署的商務用 Skype 目錄林都必須完全保持在內部部署 (且可互相同盟)。 請注意, 如果您想[要使用新功能來停](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)用從2018年12月起提供的線上 SIP 網域, 則這些其他內部部署組織可以同步處理到 AAD。

    在多個樹林中部署商務用 Skype 的客戶, 必須使用分割網域 (共用 SIP 位址空間) 功能, 將每個商務用 skype 目錄林分別完整地遷移到 Office 365 租使用者, 然後再停用混合式內部部署, 在繼續之前, 您必須先開始進行商務用 Skype 部署。 此外, 在遷移到雲端之前, 內部部署使用者會與任何不在相同使用者的內部部署目錄中的使用者保持聯合狀態。 如需詳細資訊, 請參閱[小組和商務用 Skype 的雲端整合](cloud-consolidation.md)。

## <a name="federation-requirements"></a>同盟需求

<a name="BKMK_Federation"> </a>

配置混合式時, 您必須確保您的內部部署和線上環境可以彼此相互聯盟。  線上環境預設為開啟同盟;預設情況下, 內部部署環境通常會有關閉的同盟。  

若要成功設定混合式部署, 必須符合下列需求:

- 您的內部部署和 Office 365 租使用者的網域相符設定必須相同。 如果在內部部署部署上啟用合作夥伴探索, 則必須針對您的線上租使用者設定開啟同盟。 如果未啟用合作夥伴探索, 則必須針對您的線上租使用者設定關閉的同盟。
- 內部部署部署中的 [封鎖的網域] 清單必須完全符合您線上租使用者的封鎖網域清單。
- 內部部署部署中的 [允許的網域] 清單必須完全符合您線上租使用者的「允許」網域清單。
- 線上租使用者的外部通訊必須啟用同盟。

## <a name="network-considerations"></a>網路考慮

下列各節說明下列事項:

- DNS 設定
- 防火牆考慮

### <a name="dns-settings"></a>DNS 設定

<a name="BKMK_DNS"> </a>

針對混合式部署建立 DNS 記錄時, 所有商務用 Skype 外部 DNS 記錄都必須指向內部部署基礎結構。 如需必要 DNS 記錄的詳細資料, 請參閱[商務用 Skype Server 的 DNS 需求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。

此外, 您必須確認下表所述的 DNS 解析度適用于內部部署。 (如果您已將同盟設定為內部部署, 則您很可能已經有這些。)

|DNS 記錄  <br/> |可解析的方式  <br/> |DNS 需求  <br/> |
|:-----|:-----|:-----|
|_Sipfederationtls _tcp 的 DNS SRV 記錄。\<針對\>所有支援的 SIP 網域 Sipdomain.com, 解析為存取邊緣外部 IP (s)  <br/> |Edge 伺服器  <br/> |在混合式設定中啟用聯盟通訊。 Edge 伺服器需要知道在內部部署與線上之間分割之 SIP 網域的聯盟流量。  <br/> 您必須在使用者名稱和 SRV 記錄中, 使用嚴格的 DNS 名稱符合您的網域。  <br/> |
|針對 Edge Web 會議服務 FQDN 的 DNS A 記錄, 例如 webcon.contoso.com 解析為網路會議 Edge 外部 IP (s)  <br/> |已連接內部公司網路的使用者電腦  <br/> |讓線上使用者在內部部署的託管會議中展示或查看內容。 內容包括 PowerPoint 檔案、白板、投票和共用筆記。  <br/> |

根據貴組織中的 DNS 設定方式, 您可能需要將這些記錄新增到對應 SIP 網域的內部託管 DNS 區域中, 以提供這些記錄的內部 DNS 解析。

### <a name="firewall-considerations"></a>防火牆考慮

<a name="BKMK_Firewall"> </a>

您網路上的電腦必須能夠執行標準的網際網路 DNS 查閱。 如果這些電腦能達到標準的網際網路網站, 您的網路就能滿足這個需求。

根據您的 Microsoft Online 服務資料中心的位置, 您也必須設定您的網路防火牆裝置, 以根據萬用字元功能變數名稱 (例如, 所有來自 outlook.com 的\*流量) 來接受連線。 如果貴組織的防火牆不支援萬用字元名稱設定, 您將必須手動判斷您想要允許的 IP 位址範圍, 以及指定的埠。

如需詳細資訊, 包括埠和通訊協定需求的詳細資訊, 請參閱[Office 365 url 與 IP 位址範圍](https://go.microsoft.com/fwlink/p/?LinkId=252942)。
