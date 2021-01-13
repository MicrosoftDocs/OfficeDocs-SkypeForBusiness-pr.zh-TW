---
title: 新增 Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: '[定義新的 Office Web Apps Server] 嚮導會在您的部署中定義新的 Office Web Apps Server。 您填寫下列資訊：'
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828593"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="5a7c8-104">新增 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="5a7c8-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="5a7c8-105">[ **定義新的 Office Web Apps server** ] 嚮導會在您的部署中定義新的 Office Web apps server。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="5a7c8-106">您填寫下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5a7c8-106">You fill in the following information:</span></span>

 <span data-ttu-id="5a7c8-107">**Office Web Apps SERVER FQDN**：輸入將主控 Office Web Apps Server 之伺服器的完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="5a7c8-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="5a7c8-108">**Office Web Apps server 探索 URL**：輸入 Office Web apps server 的完整統一資源定位器 (URL) </span><span class="sxs-lookup"><span data-stu-id="5a7c8-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="5a7c8-109">**Office Web Apps server 探索 URL** 的預設行為是以 Office Web apps SERVER 的 FQDN 為基礎，以下列格式建立 URL： `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="5a7c8-110">在大多數的情況下，您不需要變更預設的格式。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="5a7c8-111">如果 Office Web Apps Server 和 Office Web Apps Server 探索 URL 必須不同，您可能需要變更預設的格式。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="5a7c8-112">例如，您的 Office Web Apps Server 位於周邊網路中，而且會根據位置而有不同的 URL。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="5a7c8-113">**Office Web Apps server 部署在外部網路 (，也就是周邊/網際網路)**：如果您的 Office Web apps server 位於內部防火牆之外，例如周邊網路、外部網路或其他與您的內部網路不同的網路區域，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a7c8-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5a7c8-114">See also</span></span>

[<span data-ttu-id="5a7c8-115">會議的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="5a7c8-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
