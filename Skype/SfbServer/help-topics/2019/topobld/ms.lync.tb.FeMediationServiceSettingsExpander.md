---
title: 中繼服務設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 針對 [中繼伺服器]，您可以指定下列內容：
ms.openlocfilehash: e3593fd98c9207b6dd7033e5aac26170988ae956
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096899"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="36489-103">中繼服務設定展開工具</span><span class="sxs-lookup"><span data-stu-id="36489-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="36489-104">針對 [中繼伺服器]，您可以指定下列內容：</span><span class="sxs-lookup"><span data-stu-id="36489-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="36489-105">如果您要組合轉送伺服器至前端集區或 Standard Edition Server，請選取 [組合的中繼 **伺服器已啟用**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="36489-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="36489-106">如果選擇不組合中繼伺服器，在此區段中就沒有可定義的設定。</span><span class="sxs-lookup"><span data-stu-id="36489-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="36489-p102">如果您已啟用中繼伺服器的組合，則必須在伺服器上針對傳輸層安全性 (TLS) 定義聆聽連接埠範圍。此連接埠預設為 5067。如果您選取 [啟用 TCP 連接埠]，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。這是選用的設定，您應該參考閘道或公用交換電話網路 (PSTN) 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。</span><span class="sxs-lookup"><span data-stu-id="36489-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="36489-p103">您定義與組合中繼伺服器相關聯的 PSTN 閘道。如果已經定義閘道，可以將其用來與中繼伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="36489-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="36489-p104">如果您有多個閘道與中繼伺服器相關聯，則第一個關聯的閘道將是預設閘道。如果需要選擇另一個閘道作為預設閘道，請選取您要作為預設的閘道，然後按一下 [成為預設]。若要取消成為預設的閘道，請按一下 [取消預設]。</span><span class="sxs-lookup"><span data-stu-id="36489-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="36489-117">如需定義及設定 Enterprise Edition 前端集區或 Standard Edition server 之設定的詳細資訊，請參閱 [定義及設定拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) 及 [部署轉送伺服器及定義對等](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)。</span><span class="sxs-lookup"><span data-stu-id="36489-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).</span></span>