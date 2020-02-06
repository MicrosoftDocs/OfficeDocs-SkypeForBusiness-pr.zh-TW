---
title: 商務用 Skype Server 中的企業語音所需元件
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 商務用 Skype Server 中的企業語音元件摘要。
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803103"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="f819e-103">商務用 Skype Server 中的企業語音所需元件</span><span class="sxs-lookup"><span data-stu-id="f819e-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="f819e-104">商務用 Skype Server 中的企業語音元件摘要。</span><span class="sxs-lookup"><span data-stu-id="f819e-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="f819e-105">若要部署企業語音，您的拓撲中需要下列元件。</span><span class="sxs-lookup"><span data-stu-id="f819e-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="f819e-106">一或多個轉送伺服器，可在部分設定中，在內部商務用 Skype Server、企業語音結構及公用交換電話網絡（PSTN）閘道或會話初始通訊協定之間轉換傳輸（SIP）主幹。</span><span class="sxs-lookup"><span data-stu-id="f819e-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="f819e-107">中繼伺服器是企業語音部署中最重要的元件。</span><span class="sxs-lookup"><span data-stu-id="f819e-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="f819e-108">如需詳細資訊，請參閱[商務用 Skype server 中的中繼伺服器元件](mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f819e-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="f819e-109">轉送伺服器可以與前端伺服器 collocated，或安裝為獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="f819e-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="f819e-110">PSTN 連線元件，其中可以包含 SIP trunks 或 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="f819e-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="f819e-111">如需詳細資訊，請參閱[商務用 Skype Server 中的 PSTN 連接元件](pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="f819e-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="f819e-112">[邊緣伺服器]，可讓您的使用者在貴組織的防火牆以外時使用企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="f819e-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="f819e-113">存取邊緣服務提供來自貴組織防火牆外部之商務用 Skype 使用者通話的 SIP 信號。</span><span class="sxs-lookup"><span data-stu-id="f819e-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="f819e-114">A/V 邊緣服務可讓您能夠遍歷 NAT 和防火牆。</span><span class="sxs-lookup"><span data-stu-id="f819e-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="f819e-115">使用來自企業防火牆外部之整合通訊（UC）用戶端的來電者，都依賴于個人和電話會議的 A/V 邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="f819e-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="f819e-116">A/V 驗證服務已 collocated，並為 A/V 邊緣服務提供驗證服務。</span><span class="sxs-lookup"><span data-stu-id="f819e-116">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="f819e-117">嘗試連線至 A/V 邊緣服務的外部使用者必須具備 A/V 驗證服務所提供的驗證權杖，才能進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="f819e-117">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="f819e-118">此外，某些企業語音元件會在前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="f819e-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="f819e-119">如需這些元件的詳細資訊，請參閱[商務用 Skype server 的前端伺服器 VoIP 元件](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="f819e-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

