---
title: 啟用或停用傳送封存免責聲明至同盟合作夥伴的功能
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188860"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="69969-102">在商務用 Skype Server 中啟用或停用聯盟夥伴傳送封存免責聲明</span><span class="sxs-lookup"><span data-stu-id="69969-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="69969-103">在您部署您的 Edge 伺服器並為貴組織啟用同盟後, 您應該已指定是否要將封存免責聲明自動傳送給聯盟夥伴。</span><span class="sxs-lookup"><span data-stu-id="69969-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="69969-104">如果您封存外部通訊, 您應該啟用傳送封存免責聲明。</span><span class="sxs-lookup"><span data-stu-id="69969-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="69969-105">使用本主題中的程式來變更該設定。</span><span class="sxs-lookup"><span data-stu-id="69969-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="69969-106">下列程式假設您已經為您的組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="69969-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="69969-107">如需啟用同盟的詳細資料, 請參閱[啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="69969-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="69969-108">啟用或停用將封存免責聲明傳送給聯盟夥伴</span><span class="sxs-lookup"><span data-stu-id="69969-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="69969-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="69969-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69969-110">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="69969-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="69969-111">在左側導覽列中, 按一下 [**外部使用者存取**], 然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="69969-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="69969-112">按一下 [**存取邊緣**設定] 索引標籤上的 [**全域**], 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="69969-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="69969-113">在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下, 選取或清除 [**將封存放棄免責聲明傳送給聯盟夥伴**] 核取方塊, 以啟用或停用自動傳送封存免責聲明.</span><span class="sxs-lookup"><span data-stu-id="69969-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="69969-114">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69969-114">Click **Commit**.</span></span>

<span data-ttu-id="69969-115">若要讓聯盟使用者在商務用 Skype Server 部署中與使用者共同作業, 您必須至少已將一個外部存取原則設定為支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="69969-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="69969-116">如需控制特定聯盟網域存取權的詳細資料, 請參閱[設定允許外部網域的支援](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="69969-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="69969-117">使用 Windows PowerShell Cmdlet 來啟用或停用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="69969-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="69969-118">您可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理存檔免責聲明的使用。</span><span class="sxs-lookup"><span data-stu-id="69969-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="69969-119">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="69969-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="69969-120">啟用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="69969-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="69969-121">若要啟用封存免責聲明, 請將**EnableArchivingDisclaimer**屬性的值設定為 True ($True):</span><span class="sxs-lookup"><span data-stu-id="69969-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="69969-122">停用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="69969-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="69969-123">若要停用封存免責聲明, 請將**EnableArchivingDisclaimer**屬性的值設定為 False ($False):</span><span class="sxs-lookup"><span data-stu-id="69969-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


