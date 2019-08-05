---
title: 管理網路子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在部署呼叫許可控制 (CAC) 的大多數商務用 Skype Server 部署中, 通常會有大量的子網。 因此, 通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188557"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>在商務用 Skype Server 中管理網路子網

您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理] 命令介面來管理網路子網。 在部署呼叫許可控制 (CAC) 的大多數商務用 Skype Server 部署中, 通常會有大量的子網。 因此, 通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。

您可以使用本文中的章節來查看網路子網資訊, 或建立、修改或刪除網路子網。 

## <a name="view-network-subnet-information"></a>查看網路子網資訊 

您可以使用下列程式來查看網路子網。 從商務用 Skype Server 的 [控制台] 中, 您可以建立、修改或刪除網路子網。 

### <a name="to-view-a-network-subnet"></a>若要查看網路子網

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**子網**]。

4.  在 [**子網**] 頁面上, 按一下您要查看的子網。
 
    > [!NOTE]  
    > 您一次只能查看一個子網。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路子網配置資訊

網路子網資訊可以使用 Windows PowerShell 和 CsNetworkSubnet Cmdlet 來查看。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 

### <a name="to-view-network-subnet-information"></a>若要查看網路子網資訊

  - 若要查看所有網路子網的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER:
    
        Get-CsNetworkSubnet
    
    這會傳回如下所示的資訊:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


如需詳細資訊, 請參閱[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) Cmdlet 的說明主題。


## <a name="create-or-modify-network-subnets"></a>建立或修改網路子網 

網路子網必須與網路網站建立關聯, 才能判斷屬於該子網上之主機的地理位置。 您可以使用商務用 Skype Server 的 [控制台] 來設定子網。 從商務用 Skype Server 的 [控制台] 中, 您可以建立、修改或刪除網路子網。 

在部署呼叫許可控制 (CAC) 的大多數商務用 Skype Server 部署中, 通常會有大量的子網。 因此, 通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。 您可以從該處呼叫**CsNetworkSubnet** , 並與 Windows PowerShell Cmdlet **Import-CSV**搭配使用。 透過搭配使用這些 Cmdlet, 您就可以從逗號分隔值 (.csv) 檔案朗讀子網設定, 並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例, 請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-create-a-network-subnet"></a>建立網路子網

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**子網**]。

4.  在 [**子網**] 頁面上, 按一下 [**新增**]。

5.  在 [**新子網**] 中, 在 [**子網識別碼**] 欄位中輸入一個值。 這必須是 IP 位址 (例如, 174.11.12.0), 而且必須是子網上所定義之 IP 位址範圍中的第一個位址。

6.  在 [ **Mask** ] (遮罩) 欄位中, 輸入介於1到32的數值。

    > [!NOTE]  
    > 這個值是要套用至要建立之子網上的位元遮罩。

7.  在 [**網路網站識別碼**] 中, 選取此子網所屬的網站。

8.  可選在 [**描述**] 欄位中輸入一個值, 以提供此子網無法單獨以名稱表示的詳細資訊。

9.  按一下 [認可]****。


### <a name="to-modify-a-network-subnet"></a>修改網路子網

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**子網**]。

4.  在 [**子網**] 頁面上, 按一下您要修改的子網。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯子網**] 頁面上, 您可以修改位元遮罩、相關的網路網站或描述。 如果您修改位元遮罩, 請記住, 子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。

7.  按一下 [認可]****。

## <a name="delete-network-subnets"></a>刪除網路子網

您可以使用下列程式來刪除子網。 從商務用 Skype Server 的 [控制台] 中, 您可以建立、修改或刪除網路子網。 

在部署呼叫許可控制 (CAC) 的大多數商務用 Skype Server 部署中, 通常會有大量的子網。 因此, 通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。 您可以從該處呼叫**CsNetworkSubnet** , 並與 Windows PowerShell Cmdlet **Import-CSV**搭配使用。 透過搭配使用這些 Cmdlet, 您就可以從逗號分隔值 (.csv) 檔案朗讀子網設定, 並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例, 請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-delete-a-network-subnet"></a>刪除網路子網

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**子網**]。

4.  在 [**子網**] 頁面上, 按一下您要刪除的子網。
 
    > [!NOTE]  
    > 您可以一次刪除一個以上的子網。 若要這樣做, 請按住 CTRL 並選取多個子網, 同時按住 CTRL 鍵。 或者, 若要選取所有子網, 請在 [**編輯**] 功能表上, 按一下 [全**選**]。

5.  在 [**編輯**] 功能表上, 按一下 [**刪除**]。

6.  按一下 [確定]****。


## <a name="see-also"></a>請參閱

[新-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[移除-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
