---
title: Branch Office Appliance 一般設定展開工具 (適用於 Lync Server 2010)
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
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: 若要編輯 Survivable 分支裝置或 Survivable 分支伺服器的屬性，請在 [一般] 底下設定：
ms.openlocfilehash: 5aa8a41cbe6c73cd103810c2661979cbba6bbdd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820305"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="0a384-103">Branch Office Appliance 一般設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="0a384-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="0a384-104">若要編輯 Survivable 分支裝置或 Survivable 分支伺服器的屬性，請在 **[一般**] 底下設定：</span><span class="sxs-lookup"><span data-stu-id="0a384-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="0a384-105">**FQDN**：請輸入 Survivable 分支裝置或 Survivable 分支伺服器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="0a384-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="0a384-106">**使用所有已設定的 ip 位址**，會使用 Survivable 分支裝置或 Survivable 分支伺服器上設定的 ip 位址來取得所有用途。</span><span class="sxs-lookup"><span data-stu-id="0a384-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="0a384-107">**將服務使用方式限制為選取的 IP 位址**：您可以設定不同的位址，以定義要用於 PSTN 的伺服器和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0a384-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="0a384-108">**主要 IP 位址**：您可以針對 PSTN 相關功能以外的各種用途定義及設定此 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0a384-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="0a384-109">**PSTN IP 位址**：與公用交換電話網路 (PSTN) 功能相關聯的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0a384-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="0a384-110">您可以設定**關聯**，以確保其他伺服器角色已設定，且與 Survivable 分支裝置或 Survivable 分支伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="0a384-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="0a384-111">**關聯存檔伺服器**從清單中選取您要與 Survivable 分支裝置或 Survivable 分支伺服器相關聯的存檔伺服器</span><span class="sxs-lookup"><span data-stu-id="0a384-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="0a384-112">如果您尚未建立要與此 Survivable 分支裝置或 Survivable 分支伺服器關聯的存檔伺服器，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="0a384-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="0a384-113">**關聯監視伺服器**從清單中選取您要與 Survivable 分支裝置或 Survivable 分支伺服器關聯的監視伺服器</span><span class="sxs-lookup"><span data-stu-id="0a384-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="0a384-114">如果您尚未建立要與此 Survivable 分支裝置或 Survivable 分支伺服器關聯的監視伺服器，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="0a384-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="0a384-115">**關聯邊緣池（適用于媒體元件）** 從清單中選取您要與 Survivable 分支裝置或 Survivable 分支伺服器相關聯的邊緣伺服器或 Edge 池</span><span class="sxs-lookup"><span data-stu-id="0a384-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="0a384-116">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="0a384-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="0a384-117">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="0a384-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="0a384-118">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="0a384-118">**Help** Displays this help screen.</span></span>
  

