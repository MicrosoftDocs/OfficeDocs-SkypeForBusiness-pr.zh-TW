---
title: Lync Server 2013：針對智慧卡驗證配置企業 CA
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="6b28e-102">在 Lync Server 2013 中設定智慧卡驗證的企業 CA</span><span class="sxs-lookup"><span data-stu-id="6b28e-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b28e-103">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="6b28e-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="6b28e-104">下列章節說明如何將企業根憑證授權單位（CA）設定為支援智慧卡驗證。</span><span class="sxs-lookup"><span data-stu-id="6b28e-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="6b28e-105">如需如何安裝企業根 CA 的相關資訊，請參閱在[http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)上安裝企業根憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="6b28e-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="6b28e-106">設定企業根憑證授權單位以支援智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="6b28e-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="6b28e-107">下列步驟說明如何將企業根 CA 設定為支援智慧卡驗證：</span><span class="sxs-lookup"><span data-stu-id="6b28e-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="6b28e-108">使用網域系統管理員帳戶登入企業 CA 電腦。</span><span class="sxs-lookup"><span data-stu-id="6b28e-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="6b28e-109">啟動系統管理員，然後確認已安裝憑證授權單位 Web 登記角色。</span><span class="sxs-lookup"><span data-stu-id="6b28e-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="6b28e-110">從 [**管理工具**] 功能表，開啟 [**認證機構**管理] 主控台。</span><span class="sxs-lookup"><span data-stu-id="6b28e-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="6b28e-111">在 [功能窗格] 中，展開 [**憑證授權單位**]。</span><span class="sxs-lookup"><span data-stu-id="6b28e-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="6b28e-112">以滑鼠右鍵按一下**憑證範本**，選取 [**新增**]，然後選取 [**要頒發的憑證範本**]。</span><span class="sxs-lookup"><span data-stu-id="6b28e-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="6b28e-113">選取 [**註冊代理程式**、**智慧卡使用者**和**智慧卡登**入]。</span><span class="sxs-lookup"><span data-stu-id="6b28e-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="6b28e-114">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6b28e-114">Click **OK**.</span></span>

8.  <span data-ttu-id="6b28e-115">以滑鼠右鍵按一下**憑證範本**。</span><span class="sxs-lookup"><span data-stu-id="6b28e-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="6b28e-116">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="6b28e-116">Select **Manage**.</span></span>

10. <span data-ttu-id="6b28e-117">開啟 [智慧卡] 使用者範本的屬性。</span><span class="sxs-lookup"><span data-stu-id="6b28e-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="6b28e-118">按一下 [**安全性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6b28e-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="6b28e-119">變更許可權，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b28e-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="6b28e-120">新增具有讀取/註冊（允許）許可權的個別使用者廣告帳戶，或</span><span class="sxs-lookup"><span data-stu-id="6b28e-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="6b28e-121">新增包含具有讀取/註冊（允許）許可權的智慧卡使用者的安全性群組，或</span><span class="sxs-lookup"><span data-stu-id="6b28e-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="6b28e-122">新增具有讀取/註冊（允許）許可權的 [網域使用者] 群組</span><span class="sxs-lookup"><span data-stu-id="6b28e-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

