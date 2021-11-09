---
title: 管理網路子網
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 在大多數部署通話許可控制 (CAC) 執行的商務用 Skype Server 中，通常會有大量子網。 因此，通常最好是從商務用 Skype Server 管理命令介面設定子網。
ms.openlocfilehash: 73a0f99fa35cd1b92194ce5b09d85a30d30b72e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843856"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網路子網路

您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來管理網路子網。 在大多數部署通話許可控制 (CAC) 執行的商務用 Skype Server 中，通常會有大量子網。 因此，通常最好是從商務用 Skype Server 管理命令介面設定子網。

請使用本文中的章節來查看網路子網資訊，或建立、修改或刪除網路子網。 

## <a name="view-network-subnet-information"></a>查看網路子網資訊 

您可以使用下列程序來檢視網路子網路。 您可以從商務用 Skype Server 控制台建立、修改或刪除網路子網。 

### <a name="to-view-a-network-subnet"></a>檢視網路子網路

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。

4.  在 **[子網路]** 頁面上，按一下您要檢視的子網路。
 
    > [!NOTE]
    > 您一次只能檢視一個子網路。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路子網設定資訊

您可以使用 Windows PowerShell 和 Get-CsNetworkSubnet Cmdlet 來查看網路子網資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 

### <a name="to-view-network-subnet-information"></a>若要查看網路子網資訊

  - 若要查看所有網路子網的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
    **Get-CsNetworkSubnet**
    
    如此將傳回類似如下的資訊：
    
    身分識別：172.11.15。0<br/>
    MaskBits：28<br/>
    描述：<br/>
    NetworkSiteID： Redmond<br/>
    SubnetID : 172.11.15.0<br/>


如需詳細資訊，請參閱 [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) Cmdlet 的說明主題。


## <a name="create-or-modify-network-subnets"></a>建立或修改網路子網 

網路子網必須與網路網站相關聯，以判斷屬於該子網之主機的地理位置。 您可以使用商務用 Skype Server 控制台來設定子網。 您可以從商務用 Skype Server 控制台建立、修改或刪除網路子網。 

在大多數部署通話許可控制 (CAC) 執行的商務用 Skype Server 中，通常會有大量子網。 因此，通常最好是從商務用 Skype Server 管理命令介面設定子網。 您可以從這裡呼叫 **New-CsNetworkSubnet** ，搭配 Windows PowerShell Cmdlet 匯 **入-CSV**。 透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 (.csv) 檔案並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-create-a-network-subnet"></a>建立網路子網

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。

4.  在 [ **子網** ] 頁面上，按一下 [ **新增**]。

5.  在 [ **新建子網上**] 中，于 [ **子網識別碼** ] 欄位中輸入值。 這必須是 IP 位址 (例如，174.11.12.0) ，而且必須是子網定義之 IP 位址範圍中的第一個位址。

6.  在 [ **遮罩** ] 欄位中，輸入介於1到32的數值。

    > [!NOTE]  
    > 這個值是要套用至所建立之子網的位元遮罩。

7.  在 [ **網路網站識別碼**] 中，選取此子網所屬的網站。

8.   (選用) 在 [ **描述** ] 欄位中輸入值，以提供無法獨立以名稱表示之子網的詳細資訊。

9.  按一下 **[認可]**。


### <a name="to-modify-a-network-subnet"></a>若要修改網路子網

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。

4.  在 [ **子網** ] 頁面上，按一下您要修改的子網。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 [ **編輯子網** ] 頁面上，您可以修改位元遮罩、關聯的網路網站或描述。 如果您修改位元遮罩，請記住子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。

7.  按一下 **[認可]**。

## <a name="delete-network-subnets"></a>刪除網路子網

您可以使用下列程式來刪除子網。 您可以從商務用 Skype Server 控制台建立、修改或刪除網路子網。 

在大多數部署通話許可控制 (CAC) 執行的商務用 Skype Server 中，通常會有大量子網。 因此，通常最好是從商務用 Skype Server 管理命令介面設定子網。 您可以從這裡呼叫 **New-CsNetworkSubnet** ，搭配 Windows PowerShell Cmdlet 匯 **入-CSV**。 透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 (.csv) 檔案並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-delete-a-network-subnet"></a>若要刪除網路子網

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。

4.  在 [ **子網** ] 頁面上，按一下您要刪除的子網。
 
    > [!NOTE]  
    > 您可以一次刪除一個以上的子網。 若要執行此動作，請按住 CTRL 鍵並選取多個子網，然後按住 CTRL 鍵。 或者，若要選取所有子網，請按一下 [**編輯**] 功能表上的 [全 **選**]。

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]。


## <a name="see-also"></a>另請參閱

[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)  

[CsNetworkSubnet](/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet)