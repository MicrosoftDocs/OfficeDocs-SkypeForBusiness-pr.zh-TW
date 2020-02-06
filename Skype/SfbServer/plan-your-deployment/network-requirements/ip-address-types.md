---
title: 在商務用 Skype 中設定 IP 位址類型
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
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 摘要：在執行商務用 Skype Server 前，請先查看下列 IP 位址類型考慮。
ms.openlocfilehash: 74cb0738c7c6eb0518d8ab4ed4fae7db66921bfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802113"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>在商務用 Skype 中設定 IP 位址類型

**摘要：** 在執行商務用 Skype Server 前，請先查看下列 IP 位址類型考慮。

您可以使用您在拓撲建立器中設定的拓撲設定來部署 IP 位址類型。 本節說明如何在前端伺服器、中繼伺服器和 Edge 伺服器上部署 IP 位址類型。

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>在前端伺服器上部署 IP 位址類型

使用拓撲建立器，執行下列程式中的步驟，在前端伺服器上部署 IP 位址類型。

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>在前端伺服器上部署 IP 位址類型

1. 在 [**企業版頂層端池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。 （或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）

2. 在 [**編輯屬性**] 對話方塊中，選取您要設定的 IP 位址類型。 針對雙堆疊設定，請選取 [**啟用 IPv4**並**啟用 IPv6**]。

   **前端伺服器池的 [編輯屬性] 對話方塊**

   - **使用所有已設定的 IP 位址**。 如果您想要允許使用電腦上定義的任何 IP 位址，請選取此選項。

     > [!NOTE]
     > 這是 IP 版本6（IPv6）配置的建議選項。

   - **將服務使用限制在選取的 IP 位址**。 選取此選項以指定要在新伺服器上使用的特定位址。 如果您選取此選項，您必須輸入 [**主要 IP 位址**] 的值。

   - [**主要 IP 位址**]。 輸入一個 IP 位址，伺服器會將它用於除公用交換電話網絡（PSTN）以外的所有通訊。 輸入的 IP 位址必須符合 [選取網址類別型] 的格式。

   - **PSTN IP 位址**。 在前端伺服器上 collocated 轉送伺服器時，定義 PSTN IP 位址。 此位址必須符合所選網址類別型的格式。

> [!NOTE]
> 安裝其他網路介面卡（Nic）以支援 PSTN IP 位址設定（或針對任何其他原因），不受支援。 如需商務用 Skype Server 支援的 NIC 配置的詳細資訊，請參閱[Lync server 2013 的伺服器硬體平臺](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>在中繼伺服器上部署 IP 位址類型

使用拓撲建立器，執行下列程式中的步驟，在中繼伺服器上部署 IP 位址類型。

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中繼伺服器上部署 IP 位址類型

- 在拓撲建立器中，在 [**轉送器池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。 （或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）

- 在 [**編輯屬性**] 對話方塊中，選取您要設定的 IP 位址類型。 針對雙堆疊設定，請選取 [**啟用 IPv4**並**啟用 IPv6**]，如下圖所示。

   **中繼伺服器池的 [編輯屬性] 對話方塊**

  - **使用所有已設定的 IP 位址**。 如果您想要允許使用電腦上定義的任何 IP 位址，請選取此選項。

    > [!NOTE]
    > 這是 IP 版本6（IPv6）配置的建議選項。

  - **將服務使用限制在選取的 IP 位址**。 選取此選項以指定要在新伺服器上使用的特定位址。 如果您選取此選項，您必須輸入 [主要 IP 位址] 的值。

  - [**主要 IP 位址**]。 輸入一個 IP 位址，伺服器會將它用於除公用交換電話網絡（PSTN）以外的所有通訊。 輸入的 IP 位址必須符合 [選取網址類別型] 的格式。

  - **PSTN IP 位址**。 在前端伺服器上 collocated 轉送伺服器時，定義 PSTN IP 位址。 此位址必須符合所選網址類別型的格式。
> [!IMPORTANT]
> 我們只支援*專用*中繼伺服器上的兩個網卡。 如果在前端 collocated 轉送 Sserver 角色，則不支援雙網卡。 

> [!NOTE]
> - 如需商務用 Skype Server 2015 支援的 NIC 配置的詳細資訊，請參閱[商務用 Skype server 2015 的硬體](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - 如需商務用 Skype Server 2019 支援的 NIC 配置的詳細資訊，請參閱[商務用 Skype server 2019 的硬體](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>在 Edge Server 上部署 IP 位址類型

使用拓撲產生器，請執行下列步驟：

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>在邊緣伺服器上部署 IP 位址類型

1. 在 [拓撲建立器] 的 [**邊緣池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。 （或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）

2. 在 [**編輯屬性**] 視窗中，選取您要支援的 IP 位址設定。

3. 針對您選取的每個網址類別型，您必須提供適當的內部和外部地址。
