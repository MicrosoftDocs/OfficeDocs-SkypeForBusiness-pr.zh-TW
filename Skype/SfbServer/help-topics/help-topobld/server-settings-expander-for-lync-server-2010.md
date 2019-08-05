---
title: Lync Server 2010 的伺服器設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: '若要編輯此電腦的屬性, 請執行下列動作:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193019"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c945e-103">Lync Server 2010 的伺服器設定擴展器</span><span class="sxs-lookup"><span data-stu-id="c945e-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="c945e-104">若要編輯此電腦的屬性, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="c945e-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="c945e-105">編輯此電腦的**完整功能變數名稱 (FQDN)** 。</span><span class="sxs-lookup"><span data-stu-id="c945e-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="c945e-106">此專案必須符合在網域名稱系統 (DNS) 中定義的電腦名稱稱, 以及與此電腦相關聯之憑證的消費者備用名稱 (SAN) 或主旨名稱 (SN.EXE)。</span><span class="sxs-lookup"><span data-stu-id="c945e-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="c945e-107">選取下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="c945e-107">You select one of the following:</span></span>
    
    <span data-ttu-id="c945e-108">**使用所有已設定的 ip 位址**: 選取此專案即可使用電腦上所有已設定的 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="c945e-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c945e-109">如果電腦有多個 IP 位址, 您必須知道與此電腦關聯的服務會將所有服務的 IP 位址都使用。</span><span class="sxs-lookup"><span data-stu-id="c945e-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="c945e-110">如果偵聽伺服器或服務預期要通訊特定的 IP 位址和埠, 則服務可能無法讓最佳選取要監聽的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c945e-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="c945e-111">**將服務使用限制為選取的 IP 位址**: 如果您想要針對此電腦將偵聽的**主要 ip 位址**定義特定 ip 位址, 以便與部署中其他電腦和池進行通訊, 請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="c945e-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="c945e-112">針對特定 IP 位址定義**PSTN IP 位址**, 電腦與服務將偵聽通訊並傳送與已定義 PSTN 閘道或 IP PBX 的通訊。</span><span class="sxs-lookup"><span data-stu-id="c945e-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

