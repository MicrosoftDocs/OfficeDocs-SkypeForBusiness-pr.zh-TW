---
title: 設定商務用 Skype 中的 IP 位址類型
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
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 摘要：在實施商務用 Skype Server 之前，複查下列的 IP 位址類型考慮。
ms.openlocfilehash: 076c0e0a3901a3c69a9c6dece73fda487cddfa8c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390905"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>設定商務用 Skype 中的 IP 位址類型

**總結：** 在實施商務用 Skype Server 之前，請複查下列的 IP 位址類型考慮。

您可以使用拓撲產生器中所設定的拓撲設定來部署 IP 位址類型。 本節說明如何在前端伺服器、轉送伺服器和 Edge Server 上部署 IP 位址類型。

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>在前端伺服器上部署 IP 位址類型

使用拓撲產生器，執行下列程式中的步驟，以在前端伺服器上部署 IP 位址類型。

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>若要在前端伺服器上部署 IP 位址類型

1. 在 [ **Enterprise Edition 前端** 集區] 底下，以滑鼠右鍵按一下集區中的伺服器，然後選取 [**編輯屬性**]。  (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) 

2. 在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。 針對雙堆疊設定，請選取 [ **啟用 IPv4** 並 **啟用 IPv6**]。

   **前端伺服器集區的 [編輯內容] 對話方塊**

   - **使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。

     > [!NOTE]
     > 此為 IP 版本 6 (IPv6) 組態的建議選項。

   - **將服務使用方式限制為選取的 IP 位址**。 選取此選項指定在新伺服器上使用的特定位址。 如果您選取此選項，則必須輸入 **主要 IP 位址** 的值。

   - **主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。

   - **PSTN IP 位址**。當中繼伺服器在前端伺服器上組合時，請定義 PSTN IP 位址。此位址必須符合所選位址類型的格式。

> [!NOTE]
> 安裝額外的網路介面卡 (Nic) 以支援 PSTN IP 位址設定 (或其他任何) 在前端伺服器上的原因，都不受支援。 如需商務用 Skype Server 支援之 NIC 設定的詳細資訊，請參閱[伺服器硬體平臺的 Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>在轉送伺服器上部署 IP 位址類型

使用拓撲產生器，執行下列程式中的步驟，以在轉送伺服器上部署 IP 位址類型。

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中繼伺服器上部署 IP 位址類型

- 在 [拓撲產生器] 的 [中繼集區 **] 下，** 于集區中的伺服器上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。  (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) 

- 在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。針對雙重堆疊設定，選取 **[啟用 IPv4]** 和 **[啟用 IPv6]**，如下圖所示。

   **中繼伺服器集區的編輯內容對話方塊**

  - **使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。

    > [!NOTE]
    > 此為 IP 版本 6 (IPv6) 組態的建議選項。

  - **將服務使用方式限制為選取的 IP 位址**。選取此選項指定在新伺服器上使用的特定位址。如果您選取此選項，您必須輸入主要 IP 位址的值。

  - **主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。

  - **PSTN IP 位址**。當中繼伺服器在前端伺服器上組合時，請定義 PSTN IP 位址。此位址必須符合所選位址類型的格式。
> [!IMPORTANT]
> 僅支援 *專用* 轉送伺服器上的兩個網卡。 如果前端的中繼 Sserver 角色是組合，則不支援雙網卡。 

> [!NOTE]
> - 如需商務用 Skype Server 2015 支援的 NIC 設定的詳細資訊，請參閱[商務用 Skype Server 2015 的硬體](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - 如需商務用 Skype Server 2019 支援的 NIC 設定的詳細資訊，請參閱[商務用 Skype Server 2019 的硬體](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>在 Edge Server 上部署 IP 位址類型

使用拓撲產生器，請執行下列步驟：

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>部署 Edge Server 上的 IP 位址類型

1. 在 [拓撲產生器] 的 [ **Edge** 集區] 底下，于集區中的伺服器上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。  (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) 

2. 在 **[編輯內容]** 視窗中，選取您要支援的 IP 位址設定。

3. 您必須針對所選取的每個位址類型提供適當的內部及外部位址。