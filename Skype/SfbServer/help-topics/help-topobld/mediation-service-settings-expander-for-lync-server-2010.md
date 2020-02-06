---
title: 中繼服務設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 您可以透過定義下列內容來編輯中繼服務的內容：
ms.openlocfilehash: d5f46fb269925ace53a317caec4d9b75b3c4bbe4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819565"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="e91b2-103">中繼服務設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="e91b2-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="e91b2-104">您可以透過定義下列內容來編輯中繼服務的內容：</span><span class="sxs-lookup"><span data-stu-id="e91b2-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="e91b2-p101">**聆聽連接埠**：定義中繼服務聆聽的 [TLS]\*\*\*\* 連接埠。連接埠值預設為 TCP 5067 (透過傳輸層安全性 (TLS))</span><span class="sxs-lookup"><span data-stu-id="e91b2-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="e91b2-p102">或者，定義 [TCP]\*\*\*\* 連接埠值。預設值為 TCP 5068。</span><span class="sxs-lookup"><span data-stu-id="e91b2-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e91b2-p103">選取 [啟用 TCP 連接埠]\*\*\*\* 即可啟用 TCP 連接埠值設定。您應該參考公用交換電話網路 (PSTN) 閘道或網際網路通訊協定專用交換機 (IP-PBX) 文件中，有關與中繼服務通訊所需的連接埠設定需求。</span><span class="sxs-lookup"><span data-stu-id="e91b2-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="e91b2-111">您可以啟用 TCP 連接埠\*\*\*\* 定義從 PSTN 閘道或 IP-PBX 進行通訊的 TCP 連接埠值。</span><span class="sxs-lookup"><span data-stu-id="e91b2-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="e91b2-112">目前相關聯及現有的 [主幹]\*\*\*\* (亦即工作階段初始通訊協定 (SIP) 主幹)、[閘道]\*\*\*\* (PSTN 閘道或 IP-PBX) 及 [網站]\*\*\*\* (為主幹和閘道設定的網站) 清單。</span><span class="sxs-lookup"><span data-stu-id="e91b2-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="e91b2-p104">您可以選取 [主幹]、[閘道] 及 [站台]，然後按一下 [成為預設]\*\*\*\* 將這些選項設為此中繼服務的預設值。您也可以選取目前的預設值，然後按一下 [取消預設]\*\*\*\* 移除這些選項，使其不再是目前的預設值，然後選取新的預設值，再按一下 [成為預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e91b2-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="e91b2-116">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="e91b2-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="e91b2-117">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e91b2-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="e91b2-118">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="e91b2-118">**Help** Displays this help screen.</span></span>
  

