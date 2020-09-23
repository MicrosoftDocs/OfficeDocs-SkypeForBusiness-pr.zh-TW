---
title: Edge 電腦設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要以單一 Edge Server 或 Edge 集區中的成員電腦的身分編輯 Edge Server 電腦的屬性，請設定伺服器名稱及 IP 位址設定設定：
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218924"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="32d7b-103">Edge 電腦設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="32d7b-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="32d7b-104">若要以單一 Edge Server 或 Edge 集區中的成員電腦的身分編輯 Edge Server 電腦的屬性，請設定 **伺服器名稱及 IP 位址** 設定設定：</span><span class="sxs-lookup"><span data-stu-id="32d7b-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="32d7b-105">**內部名稱或 FQDN**：輸入網域名稱系統 (DNS) 中所參照的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="32d7b-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="32d7b-106">**Internal IPv4 address**：輸入這部電腦之內部網路介面卡 (NIC) 的 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="32d7b-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="32d7b-107">設定與此電腦相關聯的**Access Edge service** **外部 IPv4 位址**</span><span class="sxs-lookup"><span data-stu-id="32d7b-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="32d7b-108">如果您選擇使用單一 IP 位址進行 Edge Server 設定，則只能編輯 Access Edge service 的外部 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="32d7b-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="32d7b-109">其他 Edge 服務會與 Access Edge service 共用相同的 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="32d7b-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="32d7b-110">若可編輯，請設定**Web 會議服務**與此電腦相關聯的**外部 IPv4 位址**</span><span class="sxs-lookup"><span data-stu-id="32d7b-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="32d7b-111">若可供編輯，您可以設定與此電腦相關聯的**A/V Edge service** **外部 IPv4 位址**</span><span class="sxs-lookup"><span data-stu-id="32d7b-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="32d7b-112">若可供編輯，請設定與此電腦相關聯且 **已啟用 NAT 的公用 IPv4 位址** 。</span><span class="sxs-lookup"><span data-stu-id="32d7b-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="32d7b-113">只有在您選擇為 A/V Edge service 提供網路位址轉譯 (NAT) 時，才可編輯 **啟用 NAT 之公開 IPv4 位址** 的 configuration 屬性。</span><span class="sxs-lookup"><span data-stu-id="32d7b-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="32d7b-114">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="32d7b-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="32d7b-115">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="32d7b-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="32d7b-116">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="32d7b-116">**Help** Displays this help screen.</span></span>
  

