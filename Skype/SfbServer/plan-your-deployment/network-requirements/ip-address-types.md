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
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="5ad82-103">在商務用 Skype 中設定 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="5ad82-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="5ad82-104">**摘要：** 在執行商務用 Skype Server 前，請先查看下列 IP 位址類型考慮。</span><span class="sxs-lookup"><span data-stu-id="5ad82-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="5ad82-105">您可以使用您在拓撲建立器中設定的拓撲設定來部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="5ad82-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="5ad82-106">本節說明如何在前端伺服器、中繼伺服器和 Edge 伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="5ad82-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="5ad82-107">在前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="5ad82-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="5ad82-108">使用拓撲建立器，執行下列程式中的步驟，在前端伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="5ad82-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="5ad82-109">在前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="5ad82-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="5ad82-110">在 [**企業版頂層端池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="5ad82-110">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="5ad82-111">（或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）</span><span class="sxs-lookup"><span data-stu-id="5ad82-111">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="5ad82-112">在 [**編輯屬性**] 對話方塊中，選取您要設定的 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="5ad82-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="5ad82-113">針對雙堆疊設定，請選取 [**啟用 IPv4**並**啟用 IPv6**]。</span><span class="sxs-lookup"><span data-stu-id="5ad82-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="5ad82-114">**前端伺服器池的 [編輯屬性] 對話方塊**</span><span class="sxs-lookup"><span data-stu-id="5ad82-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="5ad82-115">**使用所有已設定的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="5ad82-115">**Use all configured IP addresses**.</span></span> <span data-ttu-id="5ad82-116">如果您想要允許使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="5ad82-116">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5ad82-117">這是 IP 版本6（IPv6）配置的建議選項。</span><span class="sxs-lookup"><span data-stu-id="5ad82-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="5ad82-118">**將服務使用限制在選取的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="5ad82-118">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="5ad82-119">選取此選項以指定要在新伺服器上使用的特定位址。</span><span class="sxs-lookup"><span data-stu-id="5ad82-119">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="5ad82-120">如果您選取此選項，您必須輸入 [**主要 IP 位址**] 的值。</span><span class="sxs-lookup"><span data-stu-id="5ad82-120">If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="5ad82-121">[**主要 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="5ad82-121">**Primary IP address**.</span></span> <span data-ttu-id="5ad82-122">輸入一個 IP 位址，伺服器會將它用於除公用交換電話網絡（PSTN）以外的所有通訊。</span><span class="sxs-lookup"><span data-stu-id="5ad82-122">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="5ad82-123">輸入的 IP 位址必須符合 [選取網址類別型] 的格式。</span><span class="sxs-lookup"><span data-stu-id="5ad82-123">The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="5ad82-124">**PSTN IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="5ad82-124">**PSTN IP address**.</span></span> <span data-ttu-id="5ad82-125">在前端伺服器上 collocated 轉送伺服器時，定義 PSTN IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5ad82-125">Define a PSTN IP address when a Mediation Server is collocated on the Front End Server.</span></span> <span data-ttu-id="5ad82-126">此位址必須符合所選網址類別型的格式。</span><span class="sxs-lookup"><span data-stu-id="5ad82-126">This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="5ad82-127">安裝其他網路介面卡（Nic）以支援 PSTN IP 位址設定（或針對任何其他原因），不受支援。</span><span class="sxs-lookup"><span data-stu-id="5ad82-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="5ad82-128">如需商務用 Skype Server 支援的 NIC 配置的詳細資訊，請參閱[Lync server 2013 的伺服器硬體平臺](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5ad82-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="5ad82-129">在中繼伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="5ad82-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="5ad82-130">使用拓撲建立器，執行下列程式中的步驟，在中繼伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="5ad82-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="5ad82-131">在中繼伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="5ad82-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="5ad82-132">在拓撲建立器中，在 [**轉送器池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="5ad82-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="5ad82-133">（或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）</span><span class="sxs-lookup"><span data-stu-id="5ad82-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="5ad82-134">在 [**編輯屬性**] 對話方塊中，選取您要設定的 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="5ad82-134">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="5ad82-135">針對雙堆疊設定，請選取 [**啟用 IPv4**並**啟用 IPv6**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="5ad82-135">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="5ad82-136">**中繼伺服器池的 [編輯屬性] 對話方塊**</span><span class="sxs-lookup"><span data-stu-id="5ad82-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="5ad82-137">**使用所有已設定的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="5ad82-137">**Use all configured IP addresses**.</span></span> <span data-ttu-id="5ad82-138">如果您想要允許使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="5ad82-138">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ad82-139">這是 IP 版本6（IPv6）配置的建議選項。</span><span class="sxs-lookup"><span data-stu-id="5ad82-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="5ad82-140">**將服務使用限制在選取的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="5ad82-140">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="5ad82-141">選取此選項以指定要在新伺服器上使用的特定位址。</span><span class="sxs-lookup"><span data-stu-id="5ad82-141">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="5ad82-142">如果您選取此選項，您必須輸入 [主要 IP 位址] 的值。</span><span class="sxs-lookup"><span data-stu-id="5ad82-142">If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="5ad82-143">[**主要 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="5ad82-143">**Primary IP address**.</span></span> <span data-ttu-id="5ad82-144">輸入一個 IP 位址，伺服器會將它用於除公用交換電話網絡（PSTN）以外的所有通訊。</span><span class="sxs-lookup"><span data-stu-id="5ad82-144">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="5ad82-145">輸入的 IP 位址必須符合 [選取網址類別型] 的格式。</span><span class="sxs-lookup"><span data-stu-id="5ad82-145">The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="5ad82-146">**PSTN IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="5ad82-146">**PSTN IP address**.</span></span> <span data-ttu-id="5ad82-147">在前端伺服器上 collocated 轉送伺服器時，定義 PSTN IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5ad82-147">Define a PSTN IP address when a Mediation Server is collocated on the Front End Server.</span></span> <span data-ttu-id="5ad82-148">此位址必須符合所選網址類別型的格式。</span><span class="sxs-lookup"><span data-stu-id="5ad82-148">This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="5ad82-149">我們只支援*專用*中繼伺服器上的兩個網卡。</span><span class="sxs-lookup"><span data-stu-id="5ad82-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="5ad82-150">如果在前端 collocated 轉送 Sserver 角色，則不支援雙網卡。</span><span class="sxs-lookup"><span data-stu-id="5ad82-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="5ad82-151">如需商務用 Skype Server 2015 支援的 NIC 配置的詳細資訊，請參閱[商務用 Skype server 2015 的硬體](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="5ad82-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="5ad82-152">如需商務用 Skype Server 2019 支援的 NIC 配置的詳細資訊，請參閱[商務用 Skype server 2019 的硬體](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="5ad82-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="5ad82-153">在 Edge Server 上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="5ad82-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="5ad82-154">使用拓撲產生器，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5ad82-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="5ad82-155">在邊緣伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="5ad82-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="5ad82-156">在 [拓撲建立器] 的 [**邊緣池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="5ad82-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="5ad82-157">（或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）</span><span class="sxs-lookup"><span data-stu-id="5ad82-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="5ad82-158">在 [**編輯屬性**] 視窗中，選取您要支援的 IP 位址設定。</span><span class="sxs-lookup"><span data-stu-id="5ad82-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="5ad82-159">針對您選取的每個網址類別型，您必須提供適當的內部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="5ad82-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
