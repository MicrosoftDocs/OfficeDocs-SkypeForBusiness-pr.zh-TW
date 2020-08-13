---
title: Lync Server 2013：設定企業 CA 以進行智慧卡驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41f6f2fdbf30696941e97d08cd1daf2e793f63ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="18ce4-102">在 Lync Server 2013 中設定企業 CA 以進行智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="18ce4-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18ce4-103">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="18ce4-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="18ce4-104">下列章節說明如何設定企業根憑證授權單位 (CA) 以支援智慧卡驗證。</span><span class="sxs-lookup"><span data-stu-id="18ce4-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="18ce4-105">如需如何安裝企業根 CA 的詳細資訊，請參閱 Install a Enterprise Root 核證機關 at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) 。</span><span class="sxs-lookup"><span data-stu-id="18ce4-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="18ce4-106">設定企業根憑證授權以支援智慧卡驗證</span><span class="sxs-lookup"><span data-stu-id="18ce4-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="18ce4-107">下列步驟說明如何設定企業根 CA 以支援智慧卡驗證：</span><span class="sxs-lookup"><span data-stu-id="18ce4-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="18ce4-108">使用網域管理員帳戶登入 Enterprise CA 電腦。</span><span class="sxs-lookup"><span data-stu-id="18ce4-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="18ce4-109">啟動系統管理員，並確認已安裝 [憑證授權單位網站] 註冊角色。</span><span class="sxs-lookup"><span data-stu-id="18ce4-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="18ce4-110">在 [系統**管理工具**] 功能表中，開啟 [**憑證授權單位**管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="18ce4-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="18ce4-111">在功能窗格中，展開 [**憑證授權單位**單位]。</span><span class="sxs-lookup"><span data-stu-id="18ce4-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="18ce4-112">以滑鼠右鍵按一下 [**憑證範本**]，選取 [**新增**]，然後選取 [**要發出的憑證範本**]。</span><span class="sxs-lookup"><span data-stu-id="18ce4-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="18ce4-113">選取 [**註冊代理程式**、**智慧卡使用者**及**智慧卡登**入]。</span><span class="sxs-lookup"><span data-stu-id="18ce4-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="18ce4-114">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18ce4-114">Click **OK**.</span></span>

8.  <span data-ttu-id="18ce4-115">以滑鼠右鍵按一下 [**憑證範本**]。</span><span class="sxs-lookup"><span data-stu-id="18ce4-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="18ce4-116">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="18ce4-116">Select **Manage**.</span></span>

10. <span data-ttu-id="18ce4-117">開啟智慧卡使用者範本的屬性。</span><span class="sxs-lookup"><span data-stu-id="18ce4-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="18ce4-118">按一下 [**安全性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="18ce4-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="18ce4-119">變更許可權，如下所示：</span><span class="sxs-lookup"><span data-stu-id="18ce4-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="18ce4-120">使用讀取/註冊，新增個別使用者的 AD 帳戶。 (允許) 許可權，或</span><span class="sxs-lookup"><span data-stu-id="18ce4-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="18ce4-121">使用讀取/註冊，新增包含智慧卡使用者的安全性群組。 (允許) 許可權，或</span><span class="sxs-lookup"><span data-stu-id="18ce4-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="18ce4-122">新增具有讀取/註冊的網域使用者群組 (允許) 許可權</span><span class="sxs-lookup"><span data-stu-id="18ce4-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

