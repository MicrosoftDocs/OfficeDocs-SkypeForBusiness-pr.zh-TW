---
title: Branch Office Appliance 一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 若要編輯現有 Survivable 分支裝置或 Survivable 分支伺服器的設定，您會看到下列各節：
ms.openlocfilehash: fcef74d0104ef758b9ca32819fd74adee303a3a1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684876"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="e667f-103">Branch Office Appliance 一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="e667f-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="e667f-104">若要編輯現有 Survivable 分支裝置或 Survivable 分支伺服器的設定，您會看到下列各節：</span><span class="sxs-lookup"><span data-stu-id="e667f-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="e667f-105">一般設定</span><span class="sxs-lookup"><span data-stu-id="e667f-105">General settings</span></span>

- <span data-ttu-id="e667f-106">恢復設定</span><span class="sxs-lookup"><span data-stu-id="e667f-106">Resiliency settings</span></span>

- <span data-ttu-id="e667f-107">中繼伺服器設定</span><span class="sxs-lookup"><span data-stu-id="e667f-107">Mediation Server settings</span></span>



<span data-ttu-id="e667f-108">針對 Survivable 分支裝置或 Survivable 分支伺服器，您會看到下列各項：</span><span class="sxs-lookup"><span data-stu-id="e667f-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="e667f-109">一般設定</span><span class="sxs-lookup"><span data-stu-id="e667f-109">General settings</span></span>

<span data-ttu-id="e667f-110">Survivable 分支裝置或 Survivable 分支伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="e667f-110">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="e667f-111">編輯伺服器的 FQDN 會變更此值。</span><span class="sxs-lookup"><span data-stu-id="e667f-111">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="e667f-112">您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="e667f-112">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="e667f-p102">您可以選擇**使用所有設定的 IP 位址**或**將服務使用方式限制為選取的 IP 位址**。如果您選擇**將服務限制為定義的 IP 位址**，您需要定義主要 IP 位址，以供伺服器用於所有通訊 (公用交換電話網路 (PSTN) 閘道除外)。您必須定義個別的 IP 位址供 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="e667f-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="e667f-116">在 [關聯] \*\*\*\* 中，您可以編輯或指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="e667f-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="e667f-117">[關聯存檔伺服器] 可讓您選取將封存伺服器與 Survivable 分支裝置或 Survivable 分支伺服器進行關聯。</span><span class="sxs-lookup"><span data-stu-id="e667f-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="e667f-118">您可以從下拉式清單中選取伺服器來選取已定義的存檔伺服器，或按一下 [**新增**] 以指定新的存檔伺服器。</span><span class="sxs-lookup"><span data-stu-id="e667f-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e667f-119">您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e667f-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="e667f-120">[關聯監視伺服器] 可讓您選取將監視伺服器與 Survivable 分支裝置或 Survivable 分支伺服器進行關聯。</span><span class="sxs-lookup"><span data-stu-id="e667f-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="e667f-121">您可以從下拉式清單中選取伺服器來選取已定義的監視伺服器，或按一下 [**新增**] 以指定新的監視伺服器。</span><span class="sxs-lookup"><span data-stu-id="e667f-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="e667f-122">[關聯邊緣池] 可讓您選取將 Edge 伺服器或池與 Survivable 分支裝置或 Survivable 分支伺服器進行關聯。</span><span class="sxs-lookup"><span data-stu-id="e667f-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="e667f-123">您可以從下拉式清單中選取伺服器，以選取已定義的 Edge Server 或集區，或按下 [新增]\*\*\*\* 以指定新的 Edge Server 或集區。</span><span class="sxs-lookup"><span data-stu-id="e667f-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="e667f-124">恢復</span><span class="sxs-lookup"><span data-stu-id="e667f-124">Resiliency</span></span>

<span data-ttu-id="e667f-p106">恢復功能提供登錄器集區的高可用性。藉由提供備份登錄器，如果主要登錄器失敗，則備份登錄器可以接管失敗的登錄器，讓使用者能夠進行登入和通訊。視無法使用主要登錄器的系統為何而定，使用者可用的功能可能會減少。</span><span class="sxs-lookup"><span data-stu-id="e667f-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="e667f-128">從下拉式清單中，選取要充當 Survivable 分支裝置或 Survivable 分支伺服器之備份註冊機構的企業版前端池或標準版前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e667f-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="e667f-129">您也可以選擇啟用「容錯移轉」與「容錯回復」時間間隔。</span><span class="sxs-lookup"><span data-stu-id="e667f-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="e667f-130">啟用容錯移轉與容錯回復時間設定 (以秒為單位來指定) 可自動偵測失敗的登錄器，並且有容錯回復時間可自動判定主要登錄器是否已備份且可接管登錄器程序。</span><span class="sxs-lookup"><span data-stu-id="e667f-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e667f-131">定義失敗偵測和容錯回復間隔時，請小心不要讓輸入的間隔導致在登錄器短時間無法回應時，發生容錯移轉和容錯回復。</span><span class="sxs-lookup"><span data-stu-id="e667f-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="e667f-132">根據集區或伺服器的載入情形，主要登錄器可能會在短時間內無法回應。</span><span class="sxs-lookup"><span data-stu-id="e667f-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="e667f-133">Survivable 分支裝置或網站中 Survivable 分支伺服器的預設值為 [池] 或 [標準版版本前端120伺服器]，用於容錯移轉和240秒以進行回退。</span><span class="sxs-lookup"><span data-stu-id="e667f-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="e667f-134">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="e667f-134">Mediation Server</span></span>

<span data-ttu-id="e667f-135">若是**中繼伺服器**，您可以指定下列內容：</span><span class="sxs-lookup"><span data-stu-id="e667f-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="e667f-136">**已啟用 Collocated 中繼伺服器**的核取方塊無法在 Survivable 分支裝置或 Survivable 分支伺服器上使用，因為轉送伺服器是 Collocated。</span><span class="sxs-lookup"><span data-stu-id="e667f-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="e667f-137">您需要在集區伺服器上定義傳輸層安全性 (TLS) 的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="e667f-137">You define the listening port on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="e667f-138">此連接埠預設為 5067。</span><span class="sxs-lookup"><span data-stu-id="e667f-138">By default, this port is 5067.</span></span> <span data-ttu-id="e667f-139">如果您選取 [啟用 TCP 連接埠]\*\*\*\*，則必須為組合的中繼伺服器定義 TCP 連接埠。</span><span class="sxs-lookup"><span data-stu-id="e667f-139">If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server.</span></span> <span data-ttu-id="e667f-140">這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。</span><span class="sxs-lookup"><span data-stu-id="e667f-140">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="e667f-141">依預設，TCP 連接埠的值為 5068。</span><span class="sxs-lookup"><span data-stu-id="e667f-141">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="e667f-142">您可以定義與 collocated 中繼伺服器相關聯的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="e667f-142">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="e667f-143">如果您已定義閘道，就可以將它們與中繼伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e667f-143">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="e667f-144">如果尚未定義任何閘道，但您有可以定義的閘道，則可以選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e667f-144">If you have not defined any gateways, but you have them available to define, you can select **New**.</span></span> <span data-ttu-id="e667f-145">您也可以移除已針對此轉送伺服器設定的閘道。</span><span class="sxs-lookup"><span data-stu-id="e667f-145">You can also remove gateways that are already configured for this Mediation Server.</span></span> <span data-ttu-id="e667f-146">選取閘道，然後按一下 [移除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e667f-146">Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="e667f-147">如果您有多個與中繼伺服器關聯的閘道，第一個關聯的閘道就會是預設閘道。</span><span class="sxs-lookup"><span data-stu-id="e667f-147">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="e667f-148">如果您必須選擇另一個閘道作為預設閘道，請選取您要設為預設的閘道，然後按下 [成為預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e667f-148">If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e667f-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e667f-149">See also</span></span>

<span data-ttu-id="e667f-150">如需有關定義及設定 Survivable 分支裝置或 Survivable 分支伺服器設定的詳細資訊，請參閱[分支網站復原解決方案](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e667f-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


