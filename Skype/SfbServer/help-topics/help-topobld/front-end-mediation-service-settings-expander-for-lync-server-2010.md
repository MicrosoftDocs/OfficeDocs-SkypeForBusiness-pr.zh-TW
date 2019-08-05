---
title: Lync Server 2010 的前端轉送服務設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: '您可以在此對話方塊中編輯 [轉送伺服器 PSTN 閘道] 設定的屬性。 您定義下列設定:'
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189910"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="85e38-104">Lync Server 2010 的前端轉送服務設定擴展器</span><span class="sxs-lookup"><span data-stu-id="85e38-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="85e38-105">您可以在此對話方塊中編輯 [**轉送伺服器 PSTN 閘道**] 設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="85e38-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="85e38-106">您定義下列設定:</span><span class="sxs-lookup"><span data-stu-id="85e38-106">You define the following settings:</span></span>
  
- <span data-ttu-id="85e38-107">如果您想要 collocate 使用此前端伺服器或前端池的中繼伺服器, 請選取 [**已啟用的 Collocated 中繼伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="85e38-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="85e38-108">**偵聽埠**: 定義轉送伺服器將偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="85e38-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="85e38-109">您可以為**TLS**或傳輸層安全性 (或**TCP**) 或傳輸控制通訊協定定義埠。</span><span class="sxs-lookup"><span data-stu-id="85e38-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="85e38-110">若要使用 TCP 的埠專案, 您必須選取 [**啟用 TCP 埠**] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="85e38-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="85e38-111">請參閱您的公用交換電話網絡 (PSTN) 閘道的檔和設定設定, 以判斷您是否需要啟用和定義埠值 TLS、TCP 或兩者。</span><span class="sxs-lookup"><span data-stu-id="85e38-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="85e38-112">TLS 是更安全的通訊協定, 使用憑證來加密中繼伺服器與 PSTN 閘道之間的流量。</span><span class="sxs-lookup"><span data-stu-id="85e38-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="85e38-113">並非所有 PSTN 閘道都支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="85e38-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="85e38-114">目前相關聯及現有的 [主幹]\*\*\*\* (亦即工作階段初始通訊協定 (SIP) 主幹)、[閘道]\*\*\*\* (PSTN 閘道或 IP-PBX) 及 [網站]\*\*\*\* (為主幹和閘道設定的網站) 清單。</span><span class="sxs-lookup"><span data-stu-id="85e38-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="85e38-p105">您可以選取 [主幹]、[閘道] 及 [站台]，然後按一下 [成為預設]\*\*\*\* 將這些選項設為此中繼服務的預設值。您也可以選取目前的預設值，然後按一下 [取消預設]\*\*\*\* 移除這些選項，使其不再是目前的預設值，然後選取新的預設值，再按一下 [成為預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85e38-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="85e38-118">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="85e38-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="85e38-119">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="85e38-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="85e38-120">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="85e38-120">**Help** Displays this help screen.</span></span>
  

