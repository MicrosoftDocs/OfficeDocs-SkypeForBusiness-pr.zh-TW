---
title: 中繼服務設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 針對 [中繼伺服器]，您可以指定下列內容：
ms.openlocfilehash: badc56265dfab1e8c1a46f7a3d9f122ec845d162
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702178"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="2553d-103">中繼服務設定展開工具</span><span class="sxs-lookup"><span data-stu-id="2553d-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="2553d-104">針對 [中繼伺服器]\*\*\*\*，您可以指定下列內容：</span><span class="sxs-lookup"><span data-stu-id="2553d-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="2553d-105">如果您要將中繼伺服器 collocating 到前端池或標準版伺服器上，請選取 [**啟用中繼伺服器] Collocated**的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2553d-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="2553d-106">如果您選擇不 collocate 中繼伺服器，此區段中就沒有可定義的設定。</span><span class="sxs-lookup"><span data-stu-id="2553d-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="2553d-107">如果您已啟用中繼伺服器的 collocation，您必須在伺服器上定義 [傳輸層安全性（TLS）] 的偵聽埠範圍。</span><span class="sxs-lookup"><span data-stu-id="2553d-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="2553d-108">此連接埠預設為 5067。</span><span class="sxs-lookup"><span data-stu-id="2553d-108">By default, this port is 5067.</span></span> <span data-ttu-id="2553d-109">如果您選取 [啟用 TCP 連接埠]\*\*\*\*，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。</span><span class="sxs-lookup"><span data-stu-id="2553d-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="2553d-110">這是選用的設定，請參考閘道或公用交換電話網路 (PSTN) 需求來判斷是否需要這項設定。</span><span class="sxs-lookup"><span data-stu-id="2553d-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="2553d-111">依預設，TCP 連接埠的值為 5068。</span><span class="sxs-lookup"><span data-stu-id="2553d-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="2553d-112">您可以定義與 collocated 中繼伺服器相關聯的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="2553d-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="2553d-113">如果您已定義閘道，就可以將它們與中繼伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2553d-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="2553d-114">如果您有多個與中繼伺服器關聯的閘道，第一個關聯的閘道就會是預設閘道。</span><span class="sxs-lookup"><span data-stu-id="2553d-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="2553d-115">如果需要選擇另一個閘道作為預設閘道，請選取您要作為預設的閘道，然後按一下 [成為預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2553d-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="2553d-116">若要取消成為預設的閘道，請按一下 [取消預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2553d-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="2553d-117">如需有關定義及設定企業版前端池或標準版伺服器設定的詳細資料，請參閱[定義及設定拓撲](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)及[部署轉送伺服器和定義對等](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2553d-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


