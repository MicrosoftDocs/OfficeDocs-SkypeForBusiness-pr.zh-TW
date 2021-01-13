---
title: 前端中繼服務設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 您可以在此對話方塊中，編輯 [中繼伺服器 PSTN 閘道] 設定的屬性。 您可以定義下列設定：
ms.openlocfilehash: ad6aab0ce528db01621b1d43a62624d96649e66a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807053"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="401f9-104">前端中繼服務設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="401f9-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="401f9-105">您可以在此對話方塊中，編輯 [中繼伺服器 PSTN 閘道] 設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="401f9-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="401f9-106">您可以定義下列設定：</span><span class="sxs-lookup"><span data-stu-id="401f9-106">You define the following settings:</span></span>
  
- <span data-ttu-id="401f9-107">如果您想要使用此前端伺服器或前端集區來組合轉送伺服器，請選取 [ **已啟用的組合轉送伺服器** ]。</span><span class="sxs-lookup"><span data-stu-id="401f9-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="401f9-108">**聆聽埠**：定義轉送伺服器將接聽的埠。</span><span class="sxs-lookup"><span data-stu-id="401f9-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="401f9-109">您可以定義 TLS (傳輸層安全性) 或 TCP (傳輸控制通訊協定) 連接埠。</span><span class="sxs-lookup"><span data-stu-id="401f9-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="401f9-110">若要使用 TCP 連接埠項目，您必須選取 [啟用 TCP 連接埠] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="401f9-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="401f9-111">請參閱公用交換電話網路 (PSTN) 閘道的文件和組態設定，以決定是否需要啟用及定義連接埠值 TLS 及 (或) TCP。</span><span class="sxs-lookup"><span data-stu-id="401f9-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="401f9-112">TLS 是一種更安全的通訊協定，使用憑證來加密轉送伺服器和 PSTN 閘道之間的流量。</span><span class="sxs-lookup"><span data-stu-id="401f9-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="401f9-113">並非所有 PSTN 閘道都支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="401f9-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="401f9-114">目前相關聯及現有的 [主幹] (亦即工作階段初始通訊協定 (SIP) 主幹)、[閘道] (PSTN 閘道或 IP-PBX) 及 [網站] (為主幹和閘道設定的網站) 清單。</span><span class="sxs-lookup"><span data-stu-id="401f9-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="401f9-p105">您可以選取 [主幹]、[閘道] 及 [網站]，然後按一下 [成為預設] 將這些選項設為此中繼服務的預設值。您也可以選取目前的預設值，然後按一下 [取消預設] 移除這些選項，使其不再是目前的預設值，然後選取新的預設值，再按一下 [成為預設]。</span><span class="sxs-lookup"><span data-stu-id="401f9-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="401f9-118">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="401f9-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="401f9-119">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="401f9-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="401f9-120">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="401f9-120">**Help** Displays this help screen.</span></span>
  

