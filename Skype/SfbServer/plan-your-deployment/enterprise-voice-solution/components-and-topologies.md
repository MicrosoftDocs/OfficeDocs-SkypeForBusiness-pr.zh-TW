---
title: 商務用 Skype 中的通話許可控制元件與拓撲
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
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: 如果您有 MPLS 網路、SIP 幹線或協力廠商 PSTN 閘道或 PBX，請規劃通話許可控制（CAC）。 適用于商務用 Skype Server 企業版語音。
ms.openlocfilehash: 7fcbc3e8c7fc7b4139fd9c83718db59af099f47f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803113"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>商務用 Skype 中的通話許可控制元件與拓撲

如果您有 MPLS 網路、SIP 幹線或協力廠商 PSTN 閘道或 PBX，請規劃通話許可控制（CAC）。 適用于商務用 Skype Server 企業版語音。

本節中的主題提供使用各種類型的網路拓撲來部署通話許可控制（CAC）的特殊考慮事項的相關資訊。

## <a name="call-admission-control-on-an-mpls-network"></a>在 MPLS 網路上呼叫許可控制

在多協定標籤切換（MPLS）網路中，所有網站都是以全網格連接。 也就是說，所有網站都直接連線至網際網路服務提供者的 MPLS 中樞，且每個網站都配有頻寬，可跨 WAN 連結使用到 MPLS 雲端。 沒有網路中樞或中央網站可控制 IP 路由。 下圖顯示的是以 MPLS 技術為基礎的簡單網路。

**MPLS 網路範例**

![使用 MPLS 的 CAC](../../media/CAC_MPLS_1.jpg)

若要在 MPLS 網路中部署呼叫許可控制（CAC），您需要建立網路區域來代表 MPLS 雲端，並建立網路網站來代表每個 MPLS 附屬網站。 下圖說明如何設定網路區域和網路網站，以代表前圖中的範例 MPLS 網路。 整個頻寬限制和頻寬會話限制是依據從每個網路網站到代表 MPLS 雲端之網路區域的 WAN 連結容量而定。

**MPLS 網路的網路區域和網路網站**

![使用 MPLS 的通話許可控制 (CAC) 圖表](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP 主幹上的通話許可控制

若要在 SIP 主幹上部署呼叫許可控制（CAC），您需要建立網路網站來代表網際網路電話服務提供者（ITSP）。 若要在 SIP 主幹上套用頻寬原則值，您可以在企業中的網路網站和您建立用以代表 ITSP 的網路網站之間建立站間原則。

下圖顯示 SIP 主幹上的 CAC 部署範例。

**SIP 幹線上的 CAC 配置**

![通話許可控制 SIP 主幹圖表](../../media/CAC_SIP_trunk_1.jpg)

若要在 SIP 主幹上設定 CAC，您必須在 CAC 部署期間執行下列工作：

1. 建立代表 ITSP 的網路網站。 將網路網站與合適的網路區域建立關聯，並為此網路網站的音訊和影片分配零頻寬。 如需詳細資訊，請參閱在部署檔中[設定 CAC 的網路網站](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)。

    > [!NOTE]
    > 針對 ITSP，此網路網站設定無法正常運作。 在步驟2中實際會套用頻寬原則值。

2. 使用您在步驟1中建立的網站相關參數值，為 SIP 幹線建立站間連結。 例如，在企業中使用網路網站的名稱做為 NetworkSiteID1 參數的值，並使用 ITSP network 網站作為 NetworkSiteID2 參數的值。 如需詳細資訊，請參閱部署檔中的[商務用 Skype Server 中建立網路站間原則](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)，以及[新的 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)。

3. 從您的 ITSP 取得會話邊界控制器（SCB）媒體終止點的 IP 位址。 將具有子網路遮罩32的 IP 位址新增至代表 ITSP 的網路網站。 如需詳細資訊，請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>協力廠商 PSTN 閘道或 PBX 的通話許可控制

本主題說明如何將呼叫許可控制（CAC）部署在中繼伺服器的閘道介面與協力廠商公用交換電話網絡（PSTN）閘道或私人分支 exchange （PBX）之間的連結上。

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Case 1：在中繼伺服器與 PSTN 閘道之間的 CAC

在從中繼伺服器的閘道介面到協力廠商 PBX 或 PSTN 閘道的 WAN 連結上，可以部署 CAC。

**Case 1：在中繼伺服器與 PSTN 閘道之間的 CAC**

![案例 1：中繼伺服器和 PSTN 閘道間的 CAC](../../media/CAC_gateways_1.jpg)

在這個範例中，在中繼伺服器和 PSTN 閘道之間會套用 CAC。 如果網路網站1的商務用 Skype 用戶端使用者是透過 Network Site 2 中的 PSTN 閘道撥打電話給 PSTN 電話，則媒體會透過 WAN 連結流過。 因此，每個 PSTN 會話都會執行兩個 CAC 檢查：

- 在商務用 Skype 用戶端應用程式與中繼伺服器之間

- 在中繼伺服器與 PSTN 閘道之間

這適用于網路 Site 1 中的用戶端撥入 PSTN 呼叫，以及源自網路 Site 1 中用戶端應用程式的出局 PSTN 呼叫。

> [!NOTE]
> 確認 PSTN 閘道所屬的 IP 子網已設定並與網路 Site 2 相關聯。

> [!NOTE]
> 請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。

> [!NOTE]
> 如需詳細資訊，請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Case 2：在中繼伺服器與含媒體端接點的協力廠商 PBX 之間使用 CAC

此設定類似于 Case 1。 在這兩種情況下，中繼伺服器會知道在 WAN 連結的另一端終止媒體的裝置，以及具有媒體端接點（MTP）之 PSTN 閘道或 PBX 的 IP 位址，都是在轉送伺服器上設定為下一個躍點。

**Case 2：在中繼伺服器與含 MTP 的協力廠商 PBX 之間使用的 CAC**

![案例 2：中繼伺服器和具有 MTP 之 PBX 間的 CAC](../../media/CAC_gateways_2.jpg)

在這個範例中，在中繼伺服器與 PBX/MTP 之間會套用 CAC。 如果網路網站1上的商務用 Skype 用戶端使用者是透過網路 Site 2 中的 PBX/MTP 進行 PSTN 呼叫，則媒體會透過 WAN 連結流過。 因此，對於每個 PSTN 會話，都會執行兩個 CAC 檢查：

- 在商務用 Skype 用戶端應用程式與中繼伺服器之間

- 在中繼伺服器與 PBX/MTP 之間

這適用于對網路 Site 1 中的用戶端進行撥入 PSTN 呼叫，以及源自網路 Site 1 中用戶端的出局 PSTN 呼叫。

> [!NOTE]
> 確認 MTP 所屬的 IP 子網已設定並與網路 Site 2 相關聯。

> [!NOTE]
> 請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。

> [!NOTE]
> 如需詳細資訊，請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Case 3：在中繼伺服器與協力廠商 PBX 之間的 CAC （不含媒體終止點）

Case 3 與前兩個案例稍有不同。 如果在協力廠商 PBX 上沒有 MTP，那麼對於協力廠商 PBX 的傳出會話要求，中繼伺服器不知道媒體將在 PBX 邊界中終止的位置。 在這種情況下，媒體會直接在中繼伺服器與協力廠商端點裝置之間流動。

**Case 3：在中繼伺服器與沒有 MTP 的協力廠商 PBX 之間使用 CAC**

![案例 3：中繼伺服器和不具有 MTP 之 PBX 間的 CAC](../../media/CAC_gateways_3.jpg)

在這個範例中，如果網路網站1上的商務用 Skype 用戶端使用者是透過 PBX 撥打電話給使用者，則轉送伺服器只能在 proxy 腿（商務用 Skype 用戶端應用程式與中繼伺服器之間）執行 CAC 檢查。 因為在進行會話時，中繼伺服器沒有端點裝置的相關資訊，所以在通話建立之前，無法在 WAN 連結（在中繼伺服器與協力廠商端點之間）執行 CAC 檢查。 不過，在建立會話之後，中繼伺服器會針對主幹上使用的頻寬進行記帳。

針對源自協力廠商端點的呼叫，您可以在進行會話要求時，在中繼伺服器端的兩面執行 CAC 檢查時，提供該端點裝置的相關資訊。

> [!NOTE]
> 確認端點裝置所屬的 IP 子網已設定並與網路 Site 2 相關聯。

> [!NOTE]
> 請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。

> [!NOTE]
> 如需詳細資訊，請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。


