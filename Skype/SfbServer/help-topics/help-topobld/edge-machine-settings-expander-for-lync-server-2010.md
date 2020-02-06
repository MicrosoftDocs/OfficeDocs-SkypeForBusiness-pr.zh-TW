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
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要將 Edge 伺服器電腦的屬性編輯為單一邊緣伺服器或邊緣池中的成員電腦，請設定伺服器名稱和 IP 位址設定設定：
ms.openlocfilehash: b90a3a00dcb1198e696112fc3d3ded08ff00060d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820095"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b5414-103">Edge 電腦設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="b5414-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b5414-104">若要將 Edge 伺服器電腦的屬性編輯為單一邊緣伺服器或邊緣池中的成員電腦，請設定**伺服器名稱和 IP 位址**設定設定：</span><span class="sxs-lookup"><span data-stu-id="b5414-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="b5414-105">**內部名稱或 FQDN**：請輸入在網域名稱系統（DNS）中參照的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="b5414-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="b5414-106">**內部 IPv4 位址**：輸入此電腦內部網路介面卡（NIC）的 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="b5414-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="b5414-107">您可以設定與此電腦關聯的 [**存取邊緣服務\*\*\*\*外部 IPv4 位址**]</span><span class="sxs-lookup"><span data-stu-id="b5414-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b5414-108">如果您已選取針對 Edge 伺服器設定使用單一 IP 位址，您將只能編輯存取邊緣服務的外部 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="b5414-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="b5414-109">其他邊緣服務將與存取邊緣服務共用相同的 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="b5414-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="b5414-110">如果可供編輯，您可以設定**網路會議服務**與此電腦相關聯的**外部 IPv4 位址**</span><span class="sxs-lookup"><span data-stu-id="b5414-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="b5414-111">如果可供編輯，您可以設定與此電腦相關聯**的 A/V Edge 服務\*\*\*\*外部 IPv4 位址**</span><span class="sxs-lookup"><span data-stu-id="b5414-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="b5414-112">如果可供編輯，您可以設定與此電腦關聯的**NAT 啟用公用 IPv4 位址**。</span><span class="sxs-lookup"><span data-stu-id="b5414-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b5414-113">如果您選擇為 A/V 邊緣服務提供網路位址轉譯（NAT），就可以編輯**支援 NAT 之公用 IPv4 位址**的 configuration 屬性</span><span class="sxs-lookup"><span data-stu-id="b5414-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="b5414-114">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="b5414-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b5414-115">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b5414-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b5414-116">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="b5414-116">**Help** Displays this help screen.</span></span>
  

