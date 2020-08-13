---
title: Lync Server 2013： Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27a7567fa467f8e152f4b6a61b06600a127607d7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 系統管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

本主題說明 Lync Server 2013 的系統管理工具。

預設會在每一部 Lync Server 伺服器上安裝系統管理工具。 此外，您也可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。 如需安裝系統管理工具的程式，請參閱[Install Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。 如需開啟工具來執行管理工作的程式，請參閱[Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

在您安裝或使用 Lync Server 系統管理工具之前，請確定您已複查基礎結構、作業系統、軟體和系統管理員權力需求。 如需基礎結構需求的詳細資訊，請參閱[Lync Server 2013 中的系統管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。 如需作業系統和軟體需求的詳細資訊，以安裝 Lync Server 系統管理工具，請參閱 lync server [2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)，以及[Lync server 2013 中的其他伺服器支援和需求](lync-server-2013-additional-server-support-and-requirements.md)。 安裝及使用工具時所需的使用者權限，將在[設定和管理 Lync Server 2013 所需的系統管理員許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中說明。

系統管理工具包含下列工具：

  - **Lync Server 部署嚮導**    用來部署 Lync Server，並安裝所有系統管理工具。

  - **Lync Server 拓撲**     產生器用於定義部署中的元件。

  - **Lync Server 控制台**    用於使用以 web 為基礎的介面進行部署的持續管理。

  - **Lync Server 管理命令**     介面使用命令列來進行部署的持續管理。

  - **Lync Server 記錄工具**    用來疑難排解部署中的問題。

  - **集中式記錄服務**    從一部電腦、集區、網站或全域檔收集記錄檔和追蹤檔案。 選取及定義包含提供者、旗標及追蹤層級的案例。 記錄會收集、匯總及顯示工具（例如任何文字型工具或 Snooper.exe）。

您可以主要使用拓撲產生器和 Lync Server 控制台來管理您的部署。

<div>

## <a name="deployment-wizard"></a>部署嚮導

您必須使用安裝媒體上所包含的 Lync Server 部署嚮導，將所有系統管理工具安裝到尚未安裝 Lync Server 的電腦上。 在 [系統管理工具] 安裝程式期間，Lync Server 部署嚮導會與其他工具一起安裝在本機上，以便您日後使用它來安裝其他元件的檔案，或移除電腦上不想要的元件的檔。

如需如何第一次從 Lync Server 安裝媒體執行 Lync Server 部署嚮導的詳細資訊，請參閱[Install Lync server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

</div>

<div>

## <a name="topology-builder"></a>拓撲產生器

如需您可以使用拓撲產生器來執行之部署工作的詳細資訊，請參閱部署檔中的每個伺服器角色。

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 控制台

您可以使用 Lync Server 2013 控制台執行管理及維護 Lync Server 2013 所需的大部分管理工作。 Lync Server 控制台可讓您使用圖形使用者介面 (GUI) 管理執行 Lync Server 之伺服器的設定，以及組織中的使用者、用戶端和裝置。 Lync Server 管理命令介面會使用 Lync Server 控制台做為進行 Lync 伺服器設定的基礎機制。

Lync Server 控制台會自動安裝在每一部 Lync Server 前端伺服器或 Standard Edition server 上。 在這一版中，您可以遠端方式管理 Edge Server。 您也可以在另一部電腦上安裝 Lync Server 控制台，例如您想要從中集中管理 Lync Server 的管理主控台。 如需詳細資訊，請參閱[Install Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>若要使用 Lync Server 控制台設定設定，您必須使用指派給 CsAdministrator 角色的帳戶登入。 如需 Lync Server 2013 中可用的預先定義管理角色的詳細資訊，請參閱<A href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync server 2013 中規劃以角色為基礎的存取控制</A>。</P>
> <LI>
> <P>若要使用 Lync Server 控制台設定設定，您也必須使用最小螢幕解析度為 1024 x 768 的電腦。</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server 管理命令介面

在 Lync Server 中，Lync Server 管理命令介面提供一種管理和管理的新方法。 Lync Server 管理命令介面是一種強大的管理介面，可在 Windows PowerShell 命令列介面上建立，其中包含一組完整的 Lync Server 專用 Cmdlet。 透過 Lync Server 管理命令介面，您可以取得一組豐富的設定和自動化控制。 拓撲產生器和 Lync Server 控制台都會執行這些 Cmdlet 的子集，以支援 Lync Server 的管理。 Lync Server 管理命令介面包含所有 Lync Server 管理工作的 Cmdlet，您可以個別使用 Cmdlet 來管理您的部署。 如需詳細資訊，請參閱[Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔或每個 Cmdlet 的命令列說明。

</div>

<div>

## <a name="logging-tool"></a>記錄工具

Lync Server 記錄工具可在產品執行時，透過產品取得記錄和追蹤資訊，協助進行疑難排解。 您可以使用工具在任何 Lync Server 伺服器角色上執行調試會話。 如需有關記錄工具的詳細資訊，請參閱 TechNet 文件庫上的 Lync Server 2010 記錄工具檔 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) 。

<div>


> [!IMPORTANT]  
> 在所有情況下，針對 Lync Server 記錄工具的所有記錄收集建議使用集中式記錄服務。 Lync Server 記錄工具仍可運作，但如果集中式記錄服務已經在執行中，它會干擾或呈現。 您應該只使用集中式記錄服務或 Lync Server 記錄工具，但決不會同時使用。 如需集中式記錄服務的詳細資訊，以及您應以獨佔方式使用的詳細資訊，請參閱<A href="lync-server-2013-using-the-centralized-logging-service.md">在 Lync Server 2013 中使用集中式記錄服務</A>。



</div>

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的系統管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的系統管理工具軟體需求](lync-server-2013-administrative-tools-software-requirements.md)

  - [安裝和管理 Lync Server 2013 時所需的系統管理員許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [在 Lync Server 2013 中發行拓撲的需求](lync-server-2013-requirements-to-publish-a-topology.md)

  - [安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

  - [開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)

  - [疑難排解 Lync Server 2013 控制台](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [在 Lync Server 2013 中使用集中式記錄服務](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 管理命令介面](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

