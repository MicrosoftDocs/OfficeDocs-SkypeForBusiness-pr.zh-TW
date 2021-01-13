---
title: Branch Office Appliance 一般設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 若要編輯現有 Survivable Branch 裝置或 Survivable Branch 伺服器的設定，您會看到下列區段：
ms.openlocfilehash: 95f842e72066f7ef19c474b10f7293f05c83cd67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833203"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="c8949-103">Branch Office Appliance 一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="c8949-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="c8949-104">若要編輯現有 Survivable Branch 裝置或 Survivable Branch 伺服器的設定，您會看到下列區段：</span><span class="sxs-lookup"><span data-stu-id="c8949-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="c8949-105">一般設定</span><span class="sxs-lookup"><span data-stu-id="c8949-105">General settings</span></span>

- <span data-ttu-id="c8949-106">恢復能力設定</span><span class="sxs-lookup"><span data-stu-id="c8949-106">Resiliency settings</span></span>

- <span data-ttu-id="c8949-107">中繼伺服器設定</span><span class="sxs-lookup"><span data-stu-id="c8949-107">Mediation Server settings</span></span>



<span data-ttu-id="c8949-108">針對 Survivable 分支裝置或 Survivable 分支伺服器，您會看到下列各項：</span><span class="sxs-lookup"><span data-stu-id="c8949-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="c8949-109">一般設定</span><span class="sxs-lookup"><span data-stu-id="c8949-109">General settings</span></span>

<span data-ttu-id="c8949-110">Survivable Branch 裝置或 Survivable Branch 伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="c8949-110">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="c8949-111">編輯伺服器的 FQDN 會變更此值。</span><span class="sxs-lookup"><span data-stu-id="c8949-111">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="c8949-112">您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="c8949-112">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="c8949-113">您可以選取 **使用所有設定的 ip 位址** ，或將 **服務使用方式限制為選取的 ip 位址**。</span><span class="sxs-lookup"><span data-stu-id="c8949-113">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="c8949-114">如果您選取 [將 **服務限制為定義的 IP 位址**]，您將會定義伺服器用於所有通訊的主要 IP 位址，但公用交換電話網路 (PSTN) 閘道除外。</span><span class="sxs-lookup"><span data-stu-id="c8949-114">If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="c8949-115">您可以為 PSTN 使用定義個別的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c8949-115">You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="c8949-116">在 [ **關聯**] 中，您可以編輯或指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="c8949-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="c8949-117">關聯封存伺服器可讓您選取要與 Survivable 分支裝置或 Survivable Branch 伺服器建立關聯的封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="c8949-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="c8949-118">您可以從下拉式清單中選取伺服器，以選取已定義的封存伺服器，或按一下 [ **新增** ] 以指定新的封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="c8949-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c8949-119">在發佈新定義的拓撲之前，您所指定的伺服器必須存在，且必須加入網域。</span><span class="sxs-lookup"><span data-stu-id="c8949-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="c8949-120">[關聯監控伺服器] 可讓您選取要將監控伺服器與 Survivable Branch 裝置或 Survivable Branch 伺服器產生關聯。</span><span class="sxs-lookup"><span data-stu-id="c8949-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="c8949-121">您可以從下拉式清單中選取伺服器，以選取已定義的監控伺服器，或按一下 [ **新增** ] 以指定新的監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="c8949-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="c8949-122">關聯 Edge 集區可讓您選取要將 Edge Server 或集區與 Survivable Branch 裝置或 Survivable Branch 伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="c8949-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="c8949-123">您可以從下拉式清單中選取伺服器，以選取已定義的 Edge Server 或集區，或按一下 [ **新增** ] 以指定新的 edge server 或集區。</span><span class="sxs-lookup"><span data-stu-id="c8949-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="c8949-124">彈性</span><span class="sxs-lookup"><span data-stu-id="c8949-124">Resiliency</span></span>

<span data-ttu-id="c8949-125">恢復能力提供登錄器集區的高可用性。</span><span class="sxs-lookup"><span data-stu-id="c8949-125">Resiliency provides high availability for the Registrar pool.</span></span> <span data-ttu-id="c8949-126">透過提供備份註冊機構，如果主要註冊機構失敗，則備份報名者可以接管失敗的註冊機，讓使用者能夠進行登入和通訊。</span><span class="sxs-lookup"><span data-stu-id="c8949-126">By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate.</span></span> <span data-ttu-id="c8949-127">根據使用主要註冊器失敗的系統，使用者可能會降低功能。</span><span class="sxs-lookup"><span data-stu-id="c8949-127">There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="c8949-128">從下拉式清單中，選取 Enterprise Edition 前端集區或 Standard Edition 前端伺服器，該伺服器將充當 Survivable Branch 裝置或 Survivable Branch 伺服器的備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="c8949-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="c8949-129">您也可以選取啟用容錯移轉和回退時間間隔。</span><span class="sxs-lookup"><span data-stu-id="c8949-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="c8949-130">啟用容錯移轉和回退時間設定 (指定的秒數) 允許自動偵測失敗的註冊機，以及允許自動判斷主要是備份並可接管註冊機構處理常式的回退時間。</span><span class="sxs-lookup"><span data-stu-id="c8949-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8949-131">當定義失敗偵測和回退間隔時，請小心不要輸入當註冊程式在短時間內無法回應時，會發生容錯移轉和回退的間隔。</span><span class="sxs-lookup"><span data-stu-id="c8949-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="c8949-132">根據集區或伺服器的載入，主要報名者可能不會在短時間內回應。</span><span class="sxs-lookup"><span data-stu-id="c8949-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="c8949-133">Survivable 分支裝置或網站中的 Survivable 分支伺服器的預設值為集區或 Standard Edition 前端伺服器，在容錯移轉和240秒的情況下為120秒的回退。</span><span class="sxs-lookup"><span data-stu-id="c8949-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="c8949-134">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="c8949-134">Mediation Server</span></span>

<span data-ttu-id="c8949-135">針對 **[中繼伺服器]**，您可以指定下列內容：</span><span class="sxs-lookup"><span data-stu-id="c8949-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="c8949-136">Survivable Branch 裝置或 Survivable Branch 伺服器上無法使用 [ **組合轉送伺服器已啟用** ] 的核取方塊，因為轉送伺服器是組合。</span><span class="sxs-lookup"><span data-stu-id="c8949-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="c8949-137">您可以在集區伺服器上，為傳輸層安全性 (TLS) 定義接聽埠。</span><span class="sxs-lookup"><span data-stu-id="c8949-137">You define the listening port on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="c8949-138">此連接埠預設為 5067。</span><span class="sxs-lookup"><span data-stu-id="c8949-138">By default, this port is 5067.</span></span> <span data-ttu-id="c8949-139">如果您選取 [ **啟用 TCP 埠**]，則必須為組合轉送伺服器定義 TCP 埠。</span><span class="sxs-lookup"><span data-stu-id="c8949-139">If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server.</span></span> <span data-ttu-id="c8949-140">這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。</span><span class="sxs-lookup"><span data-stu-id="c8949-140">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="c8949-141">TCP 連接埠值預設為 5068。</span><span class="sxs-lookup"><span data-stu-id="c8949-141">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="c8949-p110">您定義與組合中繼伺服器相關聯的 PSTN 閘道。如果已經定義閘道，它們將可以用來與中繼伺服器相關聯。如果尚未定義任何閘道，但您有可以定義的閘道，則可以選取 **[新增]**。您也可以移除已針對此中繼伺服器設定的閘道。選取閘道，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="c8949-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="c8949-147">如果您有多個閘道與中繼伺服器相關聯，則第一個關聯的閘道將是預設閘道。</span><span class="sxs-lookup"><span data-stu-id="c8949-147">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="c8949-148">如果您必須選擇另一個閘道作為預設閘道，請選取您要設為預設的閘道，然後按一下 [ **成為預設**]。</span><span class="sxs-lookup"><span data-stu-id="c8949-148">If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8949-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c8949-149">See also</span></span>

<span data-ttu-id="c8949-150">如需定義及設定 Survivable Branch 裝置或 Survivable Branch Server 之設定的詳細資訊，請參閱 [Branch-Site 恢復性解決方案](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c8949-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


