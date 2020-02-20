---
title: 將伺服器對伺服器驗證憑證指派給 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d82974f45ab06024f2834609403ed6604067bb2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="60479-102">將伺服器對伺服器驗證憑證指派給 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60479-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60479-103">_**上次修改主題：** 2013年-10-24_</span><span class="sxs-lookup"><span data-stu-id="60479-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="60479-104">若要判斷伺服器對伺服器驗證憑證已指派給 Microsoft Lync Server 2013，請從 Lync Server 2013 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="60479-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="60479-105">如果沒有憑證資訊會傳回您必須指派權杖簽發者憑證，您才能使用伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="60479-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="60479-106">一般而言，Lync Server 2013 中的任何憑證可以做為 OAuthTokenIssuer 憑證;例如，Lync Server 2013 預設憑證也可用為 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="60479-107">（[OAUthTokenIssuer] 憑證也可以是任何的網頁伺服器憑證主旨] 欄位中包含的 SIP 網域名稱）。用於伺服器對伺服器驗證憑證的主要兩個需求是這些： 1) 相同的憑證必須設定為在所有前端伺服器; 上的 [OAuthTokenIssuer] 憑證和，2） 的憑證必須至少 2048 位元。</span><span class="sxs-lookup"><span data-stu-id="60479-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="60479-108">如果您不需要的憑證，可用於伺服器對伺服器驗證，您可以取得新的憑證，匯入新的憑證，並再將該憑證用於伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="60479-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="60479-109">您要求並取得新的憑證後您可以然後登入為任何一個前端伺服器並使用類似這樣的 Windows PowerShell 命令來匯入與指派的憑證：</span><span class="sxs-lookup"><span data-stu-id="60479-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="60479-110">在上述命令路徑參數會代表的完整路徑憑證的檔案，而 Password 參數表示已指派給憑證的密碼。</span><span class="sxs-lookup"><span data-stu-id="60479-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="60479-111">只要一次應該執行此程序： Lync Server 複寫服務會再自動建立一組的排程工作，解密，並將憑證部署至所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="60479-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="60479-112">或者，您可以使用現有的憑證作為您的伺服器對伺服器驗證憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="60479-113">（如所述的預設憑證可以當做的伺服器對伺服器驗證憑證。）下列 Windows PowerShell 命令的配對擷取預設憑證的指紋屬性的值，然後使用該值進行憑證的伺服器對伺服器驗證憑證的預設值：</span><span class="sxs-lookup"><span data-stu-id="60479-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="60479-114">在上述命令中，擷取的憑證設為擔任的全域伺服器對伺服器驗證憑證。這表示憑證會複寫至，並供所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="60479-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="60479-115">同樣地，一次，並只在一個前端伺服器，應只有執行此命令。</span><span class="sxs-lookup"><span data-stu-id="60479-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="60479-116">雖然所有前端伺服器必須使用相同的憑證，則不應在每部前端伺服器上設定的 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="60479-117">相反地，一次設定憑證，然後讓 Lync Server 複寫伺服器負責處理的每一部伺服器來複製該憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="60479-118">Set-cscertificate cmdlet 會採用憑證有問題，並立即將設定做為目前的 OAuthTokenIssuer 憑證的憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="60479-119">(Lync Server 2013 會保留兩個副本的憑證類型： 目前的憑證與先前的憑證。)如果您需要新的憑證，若要立即開始做為 [OAuthTokenIssuer] 憑證，您應該使用 Set-cscertificate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="60479-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="60479-120">您也可以使用 Set-cscertificate cmdlet 來 「 部署 」 的新憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="60479-121">「 啟用 」 的憑證就是指您設定新的憑證，在時間中成為目前的 OAuthTokenIssuer 憑證，在指定的點。</span><span class="sxs-lookup"><span data-stu-id="60479-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="60479-122">例如，此指令擷取 default 憑證，並再設定憑證作為目前的 OAuthTokenIssuer 憑證自 2012 年 7 月 1 日起接管：</span><span class="sxs-lookup"><span data-stu-id="60479-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="60479-123">在 2012 年 7 月 1 日的新憑證會被設做目前的 OAuthTokenIssuer 憑證和 「 舊 」 的 OAuthTokenIssuer 憑證會被設做先前的憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="60479-124">如果您不想要使用 Windows PowerShell 您也可以使用 [憑證] MMC 主控台來從一部前端伺服器匯出憑證，然後在所有其他前端伺服器上匯入該相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="60479-125">如果您這麼做，請確定您匯出私密金鑰] 以及本身的憑證。</span><span class="sxs-lookup"><span data-stu-id="60479-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="60479-126">在此情況下，必須在每部前端伺服器上執行程序。</span><span class="sxs-lookup"><span data-stu-id="60479-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="60479-127">當匯出和匯入憑證，在這種方式 Lync Server 2013 中的將不會複製該憑證至每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="60479-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="60479-128">所有前端伺服器已匯入憑證之後，就可以指派該憑證而不是 Windows PowerShell 中使用 Lync Server 部署精靈。</span><span class="sxs-lookup"><span data-stu-id="60479-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="60479-129">若要將憑證指派藉由使用 [部署精靈，完成下列步驟在已安裝 [部署精靈在電腦上：</span><span class="sxs-lookup"><span data-stu-id="60479-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="60479-130">按一下 [開始]、 [所有程式]、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 部署精靈**。</span><span class="sxs-lookup"><span data-stu-id="60479-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="60479-131">在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。</span><span class="sxs-lookup"><span data-stu-id="60479-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="60479-132">在 [Microsoft Lync Server 2013] 頁面上，按一下 [**執行**] 按鈕標題底下的**步驟 3： 要求、 安裝或指派憑證**。</span><span class="sxs-lookup"><span data-stu-id="60479-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="60479-133">(請注意： 如果您已經在此電腦上安裝憑證，然後**再執行一次**會標示 [**執行**] 按鈕。)</span><span class="sxs-lookup"><span data-stu-id="60479-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="60479-134">在 [憑證] 精靈中，選取 [ **OAuthTokenIssuer** ] 憑證，然後按一下 [**指派**。</span><span class="sxs-lookup"><span data-stu-id="60479-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="60479-135">在 [憑證指派精靈] 在 [**憑證指派**] 頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="60479-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="60479-136">在 [**憑證存放區**] 頁面上，選取的憑證用於伺服器對伺服器驗證，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="60479-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="60479-137">在 [憑證指派摘要] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="60479-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="60479-138">在 [執行命令] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="60479-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="60479-139">關閉 [憑證精靈] 及 [部署精靈]。</span><span class="sxs-lookup"><span data-stu-id="60479-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

