---
title: Lync Server 2013：註冊智慧卡驗證的使用者
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
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="a917a-102">在 Lync Server 2013 中註冊智慧卡驗證的使用者</span><span class="sxs-lookup"><span data-stu-id="a917a-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a917a-103">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="a917a-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="a917a-104">有兩種方法可以為使用者註冊智慧卡驗證。</span><span class="sxs-lookup"><span data-stu-id="a917a-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="a917a-105">更簡單的方法是讓使用者使用 web 註冊直接註冊智慧卡驗證，而更複雜的方法則涉及使用註冊代理程式。</span><span class="sxs-lookup"><span data-stu-id="a917a-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="a917a-106">本主題主要針對智慧卡憑證的自行註冊。</span><span class="sxs-lookup"><span data-stu-id="a917a-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="a917a-107">如需以註冊代理代表使用者註冊的詳細資訊，請參閱代表其他使用者註冊憑證[http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)。</span><span class="sxs-lookup"><span data-stu-id="a917a-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="a917a-108">註冊使用者的智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="a917a-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="a917a-109">使用啟用 Lync 的使用者認證登入 Windows 8 工作站。</span><span class="sxs-lookup"><span data-stu-id="a917a-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="a917a-110">啟動 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="a917a-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="a917a-111">流覽至 [**憑證授權單位 Web 註冊**] 頁面（ https://MyCA.contoso.com/certsrv)例如</span><span class="sxs-lookup"><span data-stu-id="a917a-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a917a-112">如果您使用的是 Internet Explorer 10，您可能需要以相容模式查看此網站。</span><span class="sxs-lookup"><span data-stu-id="a917a-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="a917a-113">在 [**歡迎**] 頁面上，選取 [**要求憑證**]。</span><span class="sxs-lookup"><span data-stu-id="a917a-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="a917a-114">接著，選取 [**高級要求**]。</span><span class="sxs-lookup"><span data-stu-id="a917a-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="a917a-115">選取 [**建立並提交此 CA 的要求**]。</span><span class="sxs-lookup"><span data-stu-id="a917a-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="a917a-116">選取 [**憑證範本**] 區段底下的 [**智慧卡使用者**]，並以下列值完成高級憑證要求：</span><span class="sxs-lookup"><span data-stu-id="a917a-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="a917a-117">[**主要選項**] 請確認他追蹤下列設定：</span><span class="sxs-lookup"><span data-stu-id="a917a-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="a917a-118">選取 [**建立新金鑰集**] 選項按鈕</span><span class="sxs-lookup"><span data-stu-id="a917a-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="a917a-119">針對**CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]</span><span class="sxs-lookup"><span data-stu-id="a917a-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="a917a-120">如需**金鑰用法**，請選取 [ **Exchange** ] （這是唯一可用的選項）。</span><span class="sxs-lookup"><span data-stu-id="a917a-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="a917a-121">針對**金鑰大小**，請輸入**2048**</span><span class="sxs-lookup"><span data-stu-id="a917a-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="a917a-122">確認已選取 [**自動金鑰容器名稱**]</span><span class="sxs-lookup"><span data-stu-id="a917a-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="a917a-123">不要選取其他方塊。</span><span class="sxs-lookup"><span data-stu-id="a917a-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="a917a-124">在 [**其他選項**] 底下，確認下列值：</span><span class="sxs-lookup"><span data-stu-id="a917a-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="a917a-125">針對**要求格式**，請選取 [ **CMC**]。</span><span class="sxs-lookup"><span data-stu-id="a917a-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="a917a-126">針對**雜湊演算法**選取 [ **sha1**]。</span><span class="sxs-lookup"><span data-stu-id="a917a-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="a917a-127">針對**易記名稱**，請輸入**Smardcard 憑證**。</span><span class="sxs-lookup"><span data-stu-id="a917a-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="a917a-128">如果您使用的是物理智慧卡讀取器，請將智慧卡插入裝置中。</span><span class="sxs-lookup"><span data-stu-id="a917a-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="a917a-129">按一下 [**提交**] 以提交證書申請。</span><span class="sxs-lookup"><span data-stu-id="a917a-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="a917a-130">出現提示時，請輸入用來建立虛擬智慧卡的 PIN。</span><span class="sxs-lookup"><span data-stu-id="a917a-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a917a-131">預設的虛擬智慧卡 PIN 值是 "12345678"。</span><span class="sxs-lookup"><span data-stu-id="a917a-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="a917a-132">在頒發憑證之後，按一下 [**安裝此憑證**] 以完成註冊程式。</span><span class="sxs-lookup"><span data-stu-id="a917a-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a917a-133">如果您的憑證要求失敗，並出現「此網頁瀏覽器不支援產生憑證要求」錯誤，有三種可能的方法可以解決此問題：</span><span class="sxs-lookup"><span data-stu-id="a917a-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="a917a-134">在 Internet Explorer 中啟用 [相容性] 視圖</span><span class="sxs-lookup"><span data-stu-id="a917a-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a917a-135">在 Internet Explorer 中啟用 [開啟 Intranet 設定] 選項</span><span class="sxs-lookup"><span data-stu-id="a917a-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a917a-136">在 Internet Explorer [選項] 功能表中，選取 [安全性] 索引標籤底下的 [重設所有區域為預設層級] 設定</span><span class="sxs-lookup"><span data-stu-id="a917a-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

