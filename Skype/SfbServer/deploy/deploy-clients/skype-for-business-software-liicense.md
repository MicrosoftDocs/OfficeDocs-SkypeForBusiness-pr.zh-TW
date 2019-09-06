---
title: Skype 會議室系統商務用 Skype 軟體授權
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 請閱讀本主題，瞭解如何檢查您是否擁有商務用 Skype 軟體大量授權。
ms.openlocfilehash: 15f768de96d65cd8584ceb2529b92892a7a94afe
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775257"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="4c75a-103">Skype 會議室系統：商務用 Skype 軟體授權</span><span class="sxs-lookup"><span data-stu-id="4c75a-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="4c75a-104">請閱讀本主題，瞭解如何檢查您是否擁有商務用 Skype 軟體大量授權。</span><span class="sxs-lookup"><span data-stu-id="4c75a-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="4c75a-105">Skype 室系統會使用已安裝的商務用 Skype 用戶端，這需要軟體大量授權。</span><span class="sxs-lookup"><span data-stu-id="4c75a-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="4c75a-106">在部署第一個 Skype 房間系統之前，請先瞭解部署的大量授權狀態-使用金鑰管理伺服器（KMS）或多個啟用金鑰（MAK）。</span><span class="sxs-lookup"><span data-stu-id="4c75a-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="4c75a-107">金鑰管理伺服器（KMS）</span><span class="sxs-lookup"><span data-stu-id="4c75a-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="4c75a-108">如果 KMS 位於適當位置，且將發佈商務用 Skype 大量授權啟用，Skype 會議室系統會自動啟動商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4c75a-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="4c75a-109">若要瞭解 KMS 是否已就緒：</span><span class="sxs-lookup"><span data-stu-id="4c75a-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="4c75a-110">從命令提示字元執行：`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="4c75a-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="4c75a-111">如需詳細資訊，請參閱[如何透過 DNS 探索 Office 和 WINDOWS KMS 主機，並移除未授權的實例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4c75a-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="4c75a-112">若要設定 KMS，請參閱[office 2013](https://technet.microsoft.com/library/ee624357.aspx)和 GVLKs 的 kms 啟用（[適用于 kms 以及 Office 2013 的 Active Directory 啟用](https://technet.microsoft.com/library/dn385360.aspx)）</span><span class="sxs-lookup"><span data-stu-id="4c75a-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="4c75a-113">Lync 的 Office 2013 一般大量授權金鑰： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R （這個按鍵會使 Skype 會議室系統在網路上尋找 KMS）。</span><span class="sxs-lookup"><span data-stu-id="4c75a-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="4c75a-114">大量授權服務中心（VLSC）的多個啟用金鑰（MAK）</span><span class="sxs-lookup"><span data-stu-id="4c75a-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="4c75a-115">如果客戶使用任何其他的大量授權軟體，IT 部門就會使用 VLSC 來管理軟體啟用和大量授權合約（VLA）。</span><span class="sxs-lookup"><span data-stu-id="4c75a-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="4c75a-116">這也會讓公司購買商務用 Skype VL 啟用，之後公司就可以取得 MAK 來在 Skype 會議室系統管理主控台中進行輸入。</span><span class="sxs-lookup"><span data-stu-id="4c75a-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="4c75a-117">擁有 VLA 的客戶必須知道他們的 VLSC 認證，這會用來管理合約及取得 MAK。</span><span class="sxs-lookup"><span data-stu-id="4c75a-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="4c75a-118">如果不確定，客戶的財務部門應該可以確認客戶是否已支付 VLA。</span><span class="sxs-lookup"><span data-stu-id="4c75a-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="4c75a-119">若要取得 MAK，請存取大量授權服務中心來查看協定，並下載產品金鑰（MAK）。</span><span class="sxs-lookup"><span data-stu-id="4c75a-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="4c75a-120">如需詳細資訊，請移至[大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4c75a-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="4c75a-121">Office 365 的 MAK，沒有 VLSC 存取權</span><span class="sxs-lookup"><span data-stu-id="4c75a-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="4c75a-122">如果客戶沒有大量授權協定，商務用 Skype 啟用的難度就會變得更難管理。</span><span class="sxs-lookup"><span data-stu-id="4c75a-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="4c75a-123">不過，沒有 VLSC 存取權的 Office 365 客戶可以提供下列資訊給 OEM 出售 Skype 會議室系統，以取得促銷 MAK：</span><span class="sxs-lookup"><span data-stu-id="4c75a-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="4c75a-124">公司名稱</span><span class="sxs-lookup"><span data-stu-id="4c75a-124">Company name</span></span>
    
- <span data-ttu-id="4c75a-125">部署連絡人名稱、電子郵件和電話號碼</span><span class="sxs-lookup"><span data-stu-id="4c75a-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="4c75a-126">部署的系統數量</span><span class="sxs-lookup"><span data-stu-id="4c75a-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="4c75a-127">部署日期</span><span class="sxs-lookup"><span data-stu-id="4c75a-127">Deployment date</span></span>
    
- <span data-ttu-id="4c75a-128">如果客戶擁有 Microsoft 技術客戶管理員，TAM 的名稱和連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="4c75a-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

