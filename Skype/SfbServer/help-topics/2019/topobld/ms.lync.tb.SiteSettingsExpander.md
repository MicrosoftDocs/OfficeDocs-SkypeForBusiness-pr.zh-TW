---
title: Lync Server 網站設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯現有網站的屬性，請執行下列操作：
ms.openlocfilehash: 30e11a6b580b80719ffd6f745c7c37edf2cf358e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805563"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="104bb-103">Lync Server 網站設定展開工具</span><span class="sxs-lookup"><span data-stu-id="104bb-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="104bb-104">若要編輯現有網站的屬性，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="104bb-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="104bb-105">網站屬性</span><span class="sxs-lookup"><span data-stu-id="104bb-105">Site properties</span></span>

<span data-ttu-id="104bb-106">在 [網站內容] 中，您可以變更或修改網站名稱 (必要) 、描述 (選用) 、城市 (optional) 、省/直轄市 (optional) ，以及國家/地區碼 (optional) 。</span><span class="sxs-lookup"><span data-stu-id="104bb-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="104bb-107">如需網站屬性的詳細資訊，請參閱 [將分支網站新增至您的拓撲](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。</span><span class="sxs-lookup"><span data-stu-id="104bb-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="104bb-108">同盟路由屬性</span><span class="sxs-lookup"><span data-stu-id="104bb-108">Federation Route properties</span></span>

<span data-ttu-id="104bb-109">若要設定網站同盟路由指派，您必須先啟用 Edge Server 或 Edge Server 集區上的同盟。</span><span class="sxs-lookup"><span data-stu-id="104bb-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="104bb-110">如果 Edge Server 或集區上沒有啟用同盟，將無法修改網站的同盟路由指派設定。</span><span class="sxs-lookup"><span data-stu-id="104bb-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="104bb-111">如果已設定 Edge Server 或集區上的同盟設定，請在網站層級選取 [ **啟用** ]。</span><span class="sxs-lookup"><span data-stu-id="104bb-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="104bb-112">然後從下拉式清單中選取 Edge 或導演，以設定為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="104bb-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="104bb-113">此設定會影響所有網站。</span><span class="sxs-lookup"><span data-stu-id="104bb-113">This setting will affect all sites.</span></span> <span data-ttu-id="104bb-114">請確定您在此網站上設定的設定適用于所有網站。</span><span class="sxs-lookup"><span data-stu-id="104bb-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="104bb-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="104bb-115">See also</span></span>

<span data-ttu-id="104bb-116">如需詳細資訊，請參閱 [外部使用者存取的拓撲](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。</span><span class="sxs-lookup"><span data-stu-id="104bb-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


