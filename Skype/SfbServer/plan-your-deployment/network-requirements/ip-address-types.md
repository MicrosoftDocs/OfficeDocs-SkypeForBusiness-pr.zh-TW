---
title: 設定商務用 Skype 中的 IP 位址類型
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：在實施商務用 Skype Server 之前，複查下列的 IP 位址類型考慮。
ms.openlocfilehash: ba10dd223e7e099d27e31bddce478603f50e49a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101249"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="01936-103">設定商務用 Skype 中的 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="01936-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="01936-104">**摘要：** 在執行商務用 Skype Server 之前，請複查下列的 IP 位址類型考慮。</span><span class="sxs-lookup"><span data-stu-id="01936-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="01936-105">您可以使用拓撲產生器中所設定的拓撲設定來部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="01936-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="01936-106">本節說明如何在前端伺服器、轉送伺服器和 Edge Server 上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="01936-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="01936-107">在前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="01936-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="01936-108">使用拓撲產生器，執行下列程式中的步驟，以在前端伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="01936-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="01936-109">若要在前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="01936-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="01936-110">在 [ **Enterprise Edition 前端** 集區] 底下的集區中，以滑鼠右鍵按一下伺服器，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="01936-110">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="01936-111"> (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) </span><span class="sxs-lookup"><span data-stu-id="01936-111">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="01936-112">在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="01936-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="01936-113">針對雙堆疊設定，請選取 [ **啟用 IPv4** 並 **啟用 IPv6**]。</span><span class="sxs-lookup"><span data-stu-id="01936-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="01936-114">**前端伺服器集區的 [編輯內容] 對話方塊**</span><span class="sxs-lookup"><span data-stu-id="01936-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="01936-p104">**使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="01936-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="01936-117">此為 IP 版本 6 (IPv6) 組態的建議選項。</span><span class="sxs-lookup"><span data-stu-id="01936-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="01936-118">**將服務使用方式限制為選取的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="01936-118">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="01936-119">選取此選項指定在新伺服器上使用的特定位址。</span><span class="sxs-lookup"><span data-stu-id="01936-119">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="01936-120">如果您選取此選項，則必須輸入 **主要 IP 位址** 的值。</span><span class="sxs-lookup"><span data-stu-id="01936-120">If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="01936-p106">**主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。</span><span class="sxs-lookup"><span data-stu-id="01936-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="01936-p107">**PSTN IP 位址**。當中繼伺服器在前端伺服器上組合時，請定義 PSTN IP 位址。此位址必須符合所選位址類型的格式。</span><span class="sxs-lookup"><span data-stu-id="01936-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="01936-127">安裝額外的網路介面卡 (Nic) 以支援 PSTN IP 位址設定 (或其他任何) 在前端伺服器上的原因，都不受支援。</span><span class="sxs-lookup"><span data-stu-id="01936-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="01936-128">如需商務用 Skype Server 支援的 NIC 設定的詳細資訊，請參閱 [伺服器硬體平臺的 Lync server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。</span><span class="sxs-lookup"><span data-stu-id="01936-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="01936-129">在轉送伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="01936-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="01936-130">使用拓撲產生器，執行下列程式中的步驟，以在轉送伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="01936-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="01936-131">在中繼伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="01936-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="01936-132">在 [拓撲產生器] 的 [中繼集區 **] 下，** 于集區中的伺服器上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="01936-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="01936-133"> (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) </span><span class="sxs-lookup"><span data-stu-id="01936-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="01936-p110">在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。針對雙重堆疊設定，選取 **[啟用 IPv4]** 和 **[啟用 IPv6]**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="01936-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="01936-136">**中繼伺服器集區的編輯內容對話方塊**</span><span class="sxs-lookup"><span data-stu-id="01936-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="01936-p111">**使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="01936-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01936-139">此為 IP 版本 6 (IPv6) 組態的建議選項。</span><span class="sxs-lookup"><span data-stu-id="01936-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="01936-p112">**將服務使用方式限制為選取的 IP 位址**。選取此選項指定在新伺服器上使用的特定位址。如果您選取此選項，您必須輸入主要 IP 位址的值。</span><span class="sxs-lookup"><span data-stu-id="01936-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="01936-p113">**主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。</span><span class="sxs-lookup"><span data-stu-id="01936-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="01936-p114">**PSTN IP 位址**。當中繼伺服器在前端伺服器上組合時，請定義 PSTN IP 位址。此位址必須符合所選位址類型的格式。</span><span class="sxs-lookup"><span data-stu-id="01936-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="01936-149">僅支援 *專用* 轉送伺服器上的兩個網卡。</span><span class="sxs-lookup"><span data-stu-id="01936-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="01936-150">如果前端的中繼 Sserver 角色是組合，則不支援雙網卡。</span><span class="sxs-lookup"><span data-stu-id="01936-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="01936-151">如需商務用 Skype Server 2015 支援的 NIC 設定的詳細資訊，請參閱 [商務用 Skype server 2015 的硬體](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="01936-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="01936-152">如需商務用 Skype Server 2019 支援的 NIC 設定的詳細資訊，請參閱 [商務用 Skype server 2019 的硬體](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="01936-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="01936-153">在 Edge Server 上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="01936-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="01936-154">使用拓撲產生器，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="01936-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="01936-155">部署 Edge Server 上的 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="01936-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="01936-156">在 [拓撲產生器] 的 [ **Edge** 集區] 底下，于集區中的伺服器上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="01936-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="01936-157"> (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) </span><span class="sxs-lookup"><span data-stu-id="01936-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="01936-158">在 **[編輯內容]** 視窗中，選取您要支援的 IP 位址設定。</span><span class="sxs-lookup"><span data-stu-id="01936-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="01936-159">您必須針對所選取的每個位址類型提供適當的內部及外部位址。</span><span class="sxs-lookup"><span data-stu-id="01936-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>