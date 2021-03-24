---
title: 裝置設定建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: 在「新增裝置設定」或「編輯裝置設定」頁面上，您可以建立或修改用以管理商務用 Skype Phone Edition 的設定集合。 這些設定可讓您設定諸如所需的安全性模式、裝置記錄等級、語音服務品質 (QoS) 設定，以及電話是否應該在指定的非使用期限後自動鎖定等事項。
ms.openlocfilehash: 47805db474169631b722cbd8e2af95ec42bc8fa6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100559"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="2824b-104">裝置組態：建立新的或編輯現有組態</span><span class="sxs-lookup"><span data-stu-id="2824b-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="2824b-105">在「 **新增裝置** 設定」或「 **編輯裝置** 設定」頁面上，您可以建立或修改用以管理商務用 Skype Phone Edition 的設定集合。</span><span class="sxs-lookup"><span data-stu-id="2824b-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="2824b-106">這些設定可讓您設定諸如所需的安全性模式、裝置記錄等級、語音服務品質 (QoS) 設定，以及電話是否應該在指定的非使用期限後自動鎖定等事項。</span><span class="sxs-lookup"><span data-stu-id="2824b-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="2824b-107">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="2824b-107">Tasks you can perform</span></span>

<span data-ttu-id="2824b-108">您可以在「 **新增裝置** 設定」或「 **編輯裝置** 設定」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="2824b-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="2824b-109">新增裝置設定。</span><span class="sxs-lookup"><span data-stu-id="2824b-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="2824b-110">修改現有裝置設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="2824b-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="2824b-111">UI 參考</span><span class="sxs-lookup"><span data-stu-id="2824b-111">UI Reference</span></span>

<span data-ttu-id="2824b-112">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="2824b-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="2824b-113">**範圍** 識別裝置設定的範圍 (Global 或 Site) 。</span><span class="sxs-lookup"><span data-stu-id="2824b-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="2824b-114">**名稱** 您可以新增或修改裝置設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="2824b-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="2824b-115">**SIP 安全性** 您可以為商務用 Skype Phone Edition 裝置設定傳輸和驗證需求。</span><span class="sxs-lookup"><span data-stu-id="2824b-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="2824b-116">您可以從下列選項中選取：</span><span class="sxs-lookup"><span data-stu-id="2824b-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="2824b-117">**低** 允許任何類型的授權或傳輸。</span><span class="sxs-lookup"><span data-stu-id="2824b-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="2824b-118">**中型** 使用者驗證需要 NTLM 或 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="2824b-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="2824b-119">**高** SIP 連線需要 NTLM 或 Kerberos 才能進行使用者驗證，而 TLS 則是必要的。</span><span class="sxs-lookup"><span data-stu-id="2824b-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="2824b-120">**記錄等級** 您可以在 UC 裝置上啟用記錄功能。</span><span class="sxs-lookup"><span data-stu-id="2824b-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="2824b-121">有效的值為： Off;低大中型和高。</span><span class="sxs-lookup"><span data-stu-id="2824b-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="2824b-122">預設值為 Off。</span><span class="sxs-lookup"><span data-stu-id="2824b-122">The default value is Off.</span></span>
    
- <span data-ttu-id="2824b-123">**語音服務品質 (QoS)** 您可以指定指派給語音流量 emanating 從商務用 Skype Phone Edition 裝置的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="2824b-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="2824b-124">預設值為40。</span><span class="sxs-lookup"><span data-stu-id="2824b-124">The default is 40.</span></span> <span data-ttu-id="2824b-125">不過，40不是一般用於音訊流量的值;相反地，音訊流量幾乎都是以 DSCP 碼46標示。</span><span class="sxs-lookup"><span data-stu-id="2824b-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="2824b-126">為了維持整個網路的一致性，您可能想要將此值變更為46。</span><span class="sxs-lookup"><span data-stu-id="2824b-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="2824b-127">**電話鎖定** 您可以指定 UC 電話是否會在經過指定的閒置期限後自動鎖定自身。</span><span class="sxs-lookup"><span data-stu-id="2824b-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="2824b-128">您可以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="2824b-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="2824b-129">**強制執行裝置鎖定** 您可以選取此核取方塊強制執行裝置鎖定。</span><span class="sxs-lookup"><span data-stu-id="2824b-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="2824b-130">**最小 PIN 碼長度** 您可以指定用於解除電話鎖定之個人識別碼 (PIN) 的最小長度。</span><span class="sxs-lookup"><span data-stu-id="2824b-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="2824b-131">PIN 碼的長度範圍是四到15位數。</span><span class="sxs-lookup"><span data-stu-id="2824b-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="2824b-132">預設長度為六位數。</span><span class="sxs-lookup"><span data-stu-id="2824b-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="2824b-133">**電話鎖定超時** 您可以指定電話鎖定自身之前的最短時間長度。</span><span class="sxs-lookup"><span data-stu-id="2824b-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="2824b-134">-超時的範圍是0到60分鐘;預設值為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="2824b-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="2824b-135">輸入值，格式為 HH： MM： SS。</span><span class="sxs-lookup"><span data-stu-id="2824b-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2824b-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2824b-136">See also</span></span>

[<span data-ttu-id="2824b-137">裝置組態</span><span class="sxs-lookup"><span data-stu-id="2824b-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="2824b-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="2824b-138">Set-CsUCPhoneConfiguration</span></span>](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)