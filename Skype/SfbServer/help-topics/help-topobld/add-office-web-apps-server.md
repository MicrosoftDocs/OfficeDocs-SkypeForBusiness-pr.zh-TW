---
title: 新增 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: '[定義新的 Office Web Apps 伺服器] 嚮導會在您的部署中定義新的 Office Web Apps 伺服器。 您填入下列資訊：'
ms.openlocfilehash: 9f0d9680e57dd55b0a4370364aff23c7f37f57a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820715"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="97f83-104">新增 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="97f83-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="97f83-105">[**定義新的 Office Web Apps 伺服器**] 嚮導會在您的部署中定義新的 Office Web apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="97f83-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="97f83-106">您填入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="97f83-106">You fill in the following information:</span></span>

 <span data-ttu-id="97f83-107">**Office Web Apps 伺服器 FQDN**：輸入將裝載 Office Web Apps 伺服器之伺服器的完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="97f83-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="97f83-108">**Office Web Apps Server 探索 URL**：輸入 Office Web apps 伺服器的完整統一資源定位器（URL）</span><span class="sxs-lookup"><span data-stu-id="97f83-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="97f83-109">**Office Web Apps server 探索 URL**的預設行為是根據格式： `https://<FQDN of the Office Web Apps Server/hosting/discovery` ，以 Office WEB apps SERVER 的 FQDN 建立 URL。</span><span class="sxs-lookup"><span data-stu-id="97f83-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="97f83-110">在大部分的情況下，您不需要變更預設格式。</span><span class="sxs-lookup"><span data-stu-id="97f83-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="97f83-111">如果 Office Web Apps Server 和 Office Web Apps Server 探索 URL 必須不同，您可能需要變更預設格式。</span><span class="sxs-lookup"><span data-stu-id="97f83-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="97f83-112">例如，您的 Office Web Apps 伺服器位於周邊網路中，並且會根據位置使用不同的 URL。</span><span class="sxs-lookup"><span data-stu-id="97f83-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="97f83-113">**Office Web Apps 伺服器已部署在外部網路（也就是 [周長/網際網路]）**：如果您的 Office Web apps 伺服器位於內部防火牆以外（例如周邊網路、外部網路或其他與您的內部網路不同的網路區域），請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="97f83-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="97f83-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="97f83-114">See also</span></span>

[<span data-ttu-id="97f83-115">會議的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="97f83-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
