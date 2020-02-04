---
title: Lync Server 2013：查看電腦上執行的服務狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984f85fca13704864b3cd47c83e8f6adca575705
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>在 Lync Server 2013 中查看電腦上執行的服務狀態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

您可以使用 Lync Server 2013 [控制台] 來查看在 Lync Server 拓撲中的特定電腦上執行的所有服務，並查看每個服務的狀態。

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>若要查看電腦上執行的服務狀態

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**拓撲**]。

4.  在 [**狀態**] 頁面上，根據需要排序或搜尋清單，以尋找您感興趣的電腦，然後按一下該電腦的名稱。

5.  請執行下列任何一項操作：
    
      - 若要查看電腦上執行的服務的最新狀態，請按一下 [**取得服務狀態**]。
    
      - 若要查看電腦上執行的特定服務清單，以及每個服務的狀態，請按一下 [**屬性**]，然後按一下 [**關閉**] 以返回清單。

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看服務狀態

您也可以使用 Windows PowerShell 和**CsWindowsService** Cmdlet 來查看服務狀態。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-service-status"></a>若要查看服務狀態

  - 若要在電腦上查看服務狀態，請在 Lync Server 管理命令介面中輸入類似以下的命令，然後按 Enter：
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    這個命令會傳回如下所示的資訊：
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

如需詳細資訊，請參閱[CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中管理裝置、電話及用戶端應用程式](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

