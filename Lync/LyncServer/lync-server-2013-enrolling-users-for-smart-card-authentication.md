---
title: Lync Server 2013：針對智慧卡驗證註冊使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfbfcd73aba4079d74074adcd2710b8a2d45aeba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526770"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="483ed-102">在 Lync Server 2013 中登記智慧卡驗證的使用者</span><span class="sxs-lookup"><span data-stu-id="483ed-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="483ed-103">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="483ed-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="483ed-104">有兩種方法可供您登記智慧卡驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="483ed-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="483ed-105">較簡單的方法是讓使用者直接註冊使用 web 註冊的智慧卡驗證，而更複雜的方法則是使用註冊代理程式。</span><span class="sxs-lookup"><span data-stu-id="483ed-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="483ed-106">本主題著重于智慧卡憑證的自我註冊。</span><span class="sxs-lookup"><span data-stu-id="483ed-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="483ed-107">如需以登錄代理程式的身分登記使用者的詳細資訊，請參閱在上註冊憑證的其他使用者 [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) 。</span><span class="sxs-lookup"><span data-stu-id="483ed-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="483ed-108">註冊使用者的智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="483ed-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="483ed-109">使用啟用 Lync 功能之使用者的認證登入 Windows 8 工作站。</span><span class="sxs-lookup"><span data-stu-id="483ed-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="483ed-110">啟動 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="483ed-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="483ed-111">流覽至 [ **憑證授權單位 Web 登記** ] 頁面 (https://MyCA.contoso.com/certsrv) 例如，</span><span class="sxs-lookup"><span data-stu-id="483ed-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="483ed-112">如果您使用的是 Internet Explorer 10，您可能需要在相容性模式中查看此網站。</span><span class="sxs-lookup"><span data-stu-id="483ed-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="483ed-113">在 [ **歡迎** ] 頁面上，選取 [ **要求憑證**]。</span><span class="sxs-lookup"><span data-stu-id="483ed-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="483ed-114">接下來，選取 [ **高級要求**]。</span><span class="sxs-lookup"><span data-stu-id="483ed-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="483ed-115">選取 [ **建立並提交此 CA 的要求**]。</span><span class="sxs-lookup"><span data-stu-id="483ed-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="483ed-116">在 [**憑證範本**] 區段中選取 [**智慧卡使用者**]，並以下列值完成「高級憑證要求」：</span><span class="sxs-lookup"><span data-stu-id="483ed-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="483ed-117">**主要選項** 確認他的下列設定：</span><span class="sxs-lookup"><span data-stu-id="483ed-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="483ed-118">選取 [ **建立新的按鍵集** ] 選項按鈕</span><span class="sxs-lookup"><span data-stu-id="483ed-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="483ed-119">若為**CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]</span><span class="sxs-lookup"><span data-stu-id="483ed-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="483ed-120">如需 **主要用法**，請選取 [ **Exchange** (這是唯一可用的選項) 。</span><span class="sxs-lookup"><span data-stu-id="483ed-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="483ed-121">若為 **金鑰大小**，請輸入 **2048**</span><span class="sxs-lookup"><span data-stu-id="483ed-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="483ed-122">確認已選取 [ **自動機碼容器名稱** ]</span><span class="sxs-lookup"><span data-stu-id="483ed-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="483ed-123">請不要選取其他方塊。</span><span class="sxs-lookup"><span data-stu-id="483ed-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="483ed-124">在 [ **其他選項** ] 下，確認下列值：</span><span class="sxs-lookup"><span data-stu-id="483ed-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="483ed-125">若為 **要求格式** ，請選取 **CMC**。</span><span class="sxs-lookup"><span data-stu-id="483ed-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="483ed-126">若為 **雜湊演算法** ，請選取 **sha1**。</span><span class="sxs-lookup"><span data-stu-id="483ed-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="483ed-127">若為 **易記名稱** ，請輸入 **Smardcard 憑證**。</span><span class="sxs-lookup"><span data-stu-id="483ed-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="483ed-128">如果您使用的是實體智慧卡讀卡機，請將智慧卡插入裝置中。</span><span class="sxs-lookup"><span data-stu-id="483ed-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="483ed-129">按一下 [ **提交** ] 提交憑證要求。</span><span class="sxs-lookup"><span data-stu-id="483ed-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="483ed-130">出現提示時，請輸入用來建立虛擬智慧卡的 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="483ed-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="483ed-131">預設虛擬智慧卡 PIN 碼值為 ' 12345678 '。</span><span class="sxs-lookup"><span data-stu-id="483ed-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="483ed-132">簽發憑證後，按一下 [ **安裝此憑證** ] 以完成註冊程式。</span><span class="sxs-lookup"><span data-stu-id="483ed-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="483ed-133">如果憑證要求失敗，錯誤為「此網頁瀏覽器不支援產生憑證要求」，有三種方法可以解決問題：</span><span class="sxs-lookup"><span data-stu-id="483ed-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="483ed-134">在 Internet Explorer 中啟用相容性檢視</span><span class="sxs-lookup"><span data-stu-id="483ed-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="483ed-135">在 Internet Explorer 中啟用 [開啟內部網路設定] 選項</span><span class="sxs-lookup"><span data-stu-id="483ed-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="483ed-136">選取 [Internet Explorer 選項] 功能表中 [安全性] 索引標籤底下的 [將所有區域重設為預設層級] 設定。</span><span class="sxs-lookup"><span data-stu-id="483ed-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

