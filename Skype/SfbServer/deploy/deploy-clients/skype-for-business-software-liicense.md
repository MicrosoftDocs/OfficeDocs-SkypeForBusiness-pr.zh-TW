---
title: Skype 會議室系統商務用 Skype 軟體授權
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 閱讀此主題以瞭解如何檢查您是否有商務用 Skype 軟體大量授權。
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113089"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="88c66-103">Skype 聊天室系統：商務用 Skype 軟體授權</span><span class="sxs-lookup"><span data-stu-id="88c66-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="88c66-104">閱讀此主題以瞭解如何檢查您是否有商務用 Skype 軟體大量授權。</span><span class="sxs-lookup"><span data-stu-id="88c66-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="88c66-105">Skype 室系統會使用已安裝的商務用 Skype 用戶端，這需要軟體大量授權。</span><span class="sxs-lookup"><span data-stu-id="88c66-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="88c66-106">在部署第一個 Skype 室系統之前，請先瞭解部署的大量授權狀態 (KMS) 或多個啟用金鑰 (MAK) 。</span><span class="sxs-lookup"><span data-stu-id="88c66-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="88c66-107"> (KMS) 的金鑰管理伺服器</span><span class="sxs-lookup"><span data-stu-id="88c66-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="88c66-108">如果 KMS 已到位，且將散佈商務用 Skype 大量授權啟用，Skype 會議室系統會自動啟用商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="88c66-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="88c66-109">若要找出 KMS 是否已到位：</span><span class="sxs-lookup"><span data-stu-id="88c66-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="88c66-110">在命令提示字元下，執行：  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="88c66-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="88c66-111">如需詳細資訊，請參閱 how [to 透過 DNS 探索 Office 和 WINDOWS KMS 主機，並移除未授權的實例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。</span><span class="sxs-lookup"><span data-stu-id="88c66-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="88c66-112">若要設定 KMS，請參閱 [office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) 和 Gvlk 的 kms 啟用， [以取得 OFFICE 2013 的 Kms 和 Active Directory 啟用](/DeployOffice/vlactivation/gvlks)</span><span class="sxs-lookup"><span data-stu-id="88c66-112">To set up a KMS, see [KMS activation of Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) and [GVLKs for KMS and Active Directory activation of Office 2013](/DeployOffice/vlactivation/gvlks)</span></span>
  
<span data-ttu-id="88c66-113">Office 2013 通用大量授權金鑰，適用于 Lync： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (此機碼會使 Skype 會議室系統在網路上尋找 KMS。 ) </span><span class="sxs-lookup"><span data-stu-id="88c66-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="88c66-114">從大量授權服務中心 (MAK) 的多重啟用金鑰 (VLSC) </span><span class="sxs-lookup"><span data-stu-id="88c66-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="88c66-115">如果客戶使用任何其他大量授權軟體，IT 部門將使用 VLSC 來管理軟體啟用和大量授權合約 (VLA) 。</span><span class="sxs-lookup"><span data-stu-id="88c66-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="88c66-116">這也會讓公司購買商務用 Skype VL 啟用，在此期間，公司可以取得 MAK 以供 Skype 聊天室系統管理主控台中輸入。</span><span class="sxs-lookup"><span data-stu-id="88c66-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="88c66-117">具有 VLA 的客戶必須知道其 VLSC 認證，其將用來管理合約並取得 MAK。</span><span class="sxs-lookup"><span data-stu-id="88c66-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="88c66-118">如果不確定，客戶的財務部門應該可以確認客戶是否已支付 VLA。</span><span class="sxs-lookup"><span data-stu-id="88c66-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="88c66-119">若要取得 MAK，請存取大量授權服務中心，以查看協定，並下載 (MAK) 中的產品金鑰。</span><span class="sxs-lookup"><span data-stu-id="88c66-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="88c66-120">如需詳細資訊，請移至 [大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="88c66-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="88c66-121">不含 VLSC 存取權的 Microsoft 365 或 Office 365 的 MAK</span><span class="sxs-lookup"><span data-stu-id="88c66-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="88c66-122">若客戶沒有大量授權合約，商務用 Skype 啟用將會困難許多。</span><span class="sxs-lookup"><span data-stu-id="88c66-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="88c66-123">不過，沒有 VLSC 存取權的 Microsoft 365 和 Office 365 客戶可以透過提供下列資訊，針對銷售 Skype 室系統的 OEM，取得促銷 MAK：</span><span class="sxs-lookup"><span data-stu-id="88c66-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="88c66-124">公司名稱</span><span class="sxs-lookup"><span data-stu-id="88c66-124">Company name</span></span>
    
- <span data-ttu-id="88c66-125">部署連絡人名稱、電子郵件和電話號碼</span><span class="sxs-lookup"><span data-stu-id="88c66-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="88c66-126">部署的系統數目</span><span class="sxs-lookup"><span data-stu-id="88c66-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="88c66-127">部署日期</span><span class="sxs-lookup"><span data-stu-id="88c66-127">Deployment date</span></span>
    
- <span data-ttu-id="88c66-128">如果客戶有 Microsoft 技術客戶經理，TAM 的名稱和連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="88c66-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
