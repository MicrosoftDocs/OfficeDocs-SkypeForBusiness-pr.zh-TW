---
title: Lync Server 2013：Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6756aee8d7c65b179fb5c1c15ca008b3bd205778
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 系統管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

本主題說明 Lync Server 2013 的管理工具。

預設會在每個 Lync Server 伺服器上安裝系統管理工具。 此外，您還可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。 如需安裝管理工具的程式，請參閱[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。 如需開啟 [工具] 以執行管理工作的程式，請參閱[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

在安裝或使用 Lync Server 管理工具之前，請務必先檢查基礎結構、作業系統、軟體及系統管理員許可權需求。 如需基礎結構需求的詳細資料，請參閱[Lync Server 2013 中的管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。 如需安裝 Lync Server 系統管理工具之作業系統和軟體需求的詳細資料，請參閱 lync [server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)，以及[Lync server 2013 中的其他伺服器支援與需求](lync-server-2013-additional-server-support-and-requirements.md)。 安裝及使用工具所需的使用者權利和許可權，會在[設定和管理 Lync Server 2013 所需的管理員權利和許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中加以說明。

管理工具組括下列各項：

  - **[Lync server 部署嚮導]**   可用於部署 Lync Server 及安裝所有系統管理工具。

  - **Lync Server 拓撲**   建立器可用來定義您部署中的元件。

  - **Lync Server [控制台**   ] 可讓您使用 web 型介面進行部署的日常管理。

  - **Lync Server Management Shell**   使用命令列來進行部署的日常管理。

  - **Lync Server 記錄工具**   用來針對您的部署問題進行疑難排解。

  - **集中式記錄服務**   從一部電腦、池、網站或全域檔收集記錄和追蹤檔案。 選取並定義包含提供者、標誌和追蹤層級的案例。 記錄會收集、匯總並與工具（例如任何以文字為基礎的工具或 Snooper）一起顯示。

您可以使用 [拓撲建立器] 和 [Lync Server 控制台] 來管理您的部署。

<div>

## <a name="deployment-wizard"></a>部署嚮導

您必須使用安裝媒體上隨附的 Lync Server 部署嚮導，將所有系統管理工具安裝到尚未安裝 Lync Server 的電腦上。 在 [管理工具] 安裝程式中，Lync Server 部署嚮導會與其他工具一起安裝在本機，以便您日後可以使用它來為其他元件安裝檔案，或移除您不想要的元件的檔案電腦.

如需有關如何第一次從 Lync Server 安裝媒體執行 Lync Server 部署嚮導的詳細資訊，請參閱[安裝 Lync server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

</div>

<div>

## <a name="topology-builder"></a>拓撲建立器

如需使用拓撲結構建立器所能執行之部署工作的詳細資訊，請參閱每個伺服器角色的部署檔。

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 控制台

您可以使用 Lync Server 2013 [控制台] 執行管理和維護 Lync Server 2013 所需的大部分系統管理工作。 Lync Server [控制台] 可讓您使用圖形使用者介面（GUI）來管理執行 Lync Server 的伺服器設定，以及組織中的使用者、用戶端和裝置。 Lync Server 管理命令介面使用 Lync Server [控制台] 做為執行 Lync Server 配置的基礎機制。

Lync Server 的 [控制台] 會自動安裝在每個 Lync Server 前端伺服器或標準版伺服器上。 在這個版本中，您會遠端系統管理邊緣伺服器。 您也可以在另一部電腦（例如，您想要集中管理 Lync Server 的管理主控台）上安裝 Lync Server [控制台]。 如需詳細資訊，請參閱[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>若要使用 Lync Server [控制台] 來設定設定，您必須使用指派給 CsAdministrator 角色的帳戶登入。 如需有關 Lync Server 2013 中預先定義的管理角色的詳細資訊，請參閱<A href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync server 2013 中規劃角色式存取控制</A>。</P>
> <LI>
> <P>若要使用 Lync Server [控制台] 設定設定，您也必須使用最小螢幕解析度為 1024 x 768 的電腦。</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server 管理命令介面

在 Lync Server 中，Lync Server 管理命令介面會提供一種管理和管理的新方法。 Lync Server 管理命令介面是在 Windows PowerShell 命令列介面上建立的強大管理介面，其中包含一組完整的 Lync Server 專用的 Cmdlet。 使用 Lync Server 管理命令介面時，您會看到一組豐富的設定和自動化控制。 [拓撲建立器] 和 [Lync Server 控制台] 都會將這些 Cmdlet 的子集都實現，以支援 Lync Server 的管理。 Lync Server 管理命令介面包含所有 Lync Server 管理工作的 Cmdlet，您可以單獨使用這些 Cmdlet 來管理您的部署。 如需詳細資訊，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔或每個 Cmdlet 的命令列說明。

</div>

<div>

## <a name="logging-tool"></a>記錄工具

Lync Server 記錄工具可在產品執行時捕獲產品的記錄及追蹤資訊，協助進行疑難排解。 您可以使用此工具在任何 Lync Server 伺服器角色上執行調試會話。 如需記錄工具的詳細資訊，請參閱 TechNet Library 上的 Lync Server 2010 記錄工具檔[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)。

<div>


> [!IMPORTANT]  
> 在任何情況下，建議針對 Lync Server 記錄工具的所有記錄收集收集集中式記錄服務。 Lync Server 記錄工具仍可正常運作，但如果集中式記錄服務已在執行，則會干擾或無法呈現。 您應該只使用集中式記錄服務或 Lync Server 記錄工具，但不要同時使用這兩個工具。 如需集中式記錄服務的詳細資訊，以及為何應以獨佔方式使用它，請參閱<A href="lync-server-2013-using-the-centralized-logging-service.md">在 Lync Server 2013 中使用集中式記錄服務</A>。



</div>

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 中的伺服器及工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的系統管理工具軟體需求](lync-server-2013-administrative-tools-software-requirements.md)

  - [設定和管理 Lync Server 2013 所需的系統管理員權限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [在 Lync Server 2013 中發行拓撲的需求](lync-server-2013-requirements-to-publish-a-topology.md)

  - [安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

  - [開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 [控制台] 的疑難排解](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [在 Lync Server 2013 中使用集中式記錄服務](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 管理命令介面](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

