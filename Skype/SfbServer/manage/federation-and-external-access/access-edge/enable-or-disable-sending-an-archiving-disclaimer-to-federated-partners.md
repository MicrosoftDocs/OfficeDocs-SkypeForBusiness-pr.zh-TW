---
title: 將封存免責聲明傳送給同盟協力廠商
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 開啟或關閉在商務用 Skype Server 中傳送封存免責聲明至同盟合作夥伴。
ms.openlocfilehash: 020ba61ed45a214466ac22e1d13cbe27563697a1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386662"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能

當您部署您的 Edge Server 並為組織啟用同盟時，您應該會指定是否要將封存免責聲明自動傳送給同盟協力廠商。 如果您封存外部通訊，應啟用傳送封存免責聲明。 使用本主題中的程式來變更該設定。

> [!NOTE]
> 下列程式假設您已經為組織啟用同盟。 如需啟用同盟的詳細資訊，請參閱 [啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>啟用或停用將封存免責聲明傳送至同盟合作夥伴的功能

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge** 設定]。

4.  在 [ **Access Edge** 設定] 索引標籤上，依序按一下 [ **全域**]、[ **編輯**] 和 [ **顯示詳細資料**]。

5.  在 [ **編輯 Access Edge** 設定] 的 [ **啟用與同盟使用者的通訊**] 下，選取或清除 [將封存 **免責聲明傳送給同盟合作夥伴** ] 核取方塊，以啟用或停用自動傳送封存免責聲明。

6.  按一下 **[認可]**。

若要讓同盟使用者能夠與您的商務用 Skype Server 部署中的使用者共同作業，您必須同時設定至少一個外部存取原則，以支援同盟使用者存取。 如需控制特定同盟網域存取權的詳細資訊，請參閱 [Configure support for 允許的外部網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用封存免責聲明

您可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理封存免責聲明。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 

## <a name="to-enable-the-archiving-disclaimer"></a>啟用封存免責聲明

  - 若要啟用封存免責聲明，請將 **EnableArchivingDisclaimer** 屬性的值設為 True ($True) ：<br/><br/>Set-CsAccessEdgeConfiguration-EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>停用封存免責聲明

  - 若要停用封存免責聲明，請將 **EnableArchivingDisclaimer** 屬性的值設為 False ($False) ：<br/><br/>Set-CsAccessEdgeConfiguration-EnableArchivingDisclaimer $False

