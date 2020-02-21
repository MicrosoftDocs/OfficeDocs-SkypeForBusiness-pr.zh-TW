---
title: Lync Server 2013： 自訂用戶端安裝
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da27eed81ea63db059a23baad511471cbe31cfe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="85228-102">自訂 Lync Server 2013 中的用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="85228-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85228-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="85228-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="85228-104">企業系統管理員可以使用本章節所討論的方法，以自訂 Office 2013 Windows Installer 型 (.msi) 安裝。</span><span class="sxs-lookup"><span data-stu-id="85228-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="85228-105">因為沒有單一工具提供所有的自訂選項，您可能將 Lync 2013 部署中使用這些方法的組合。</span><span class="sxs-lookup"><span data-stu-id="85228-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="85228-106">您至少需要使用下列章節中說明的工具：</span><span class="sxs-lookup"><span data-stu-id="85228-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="85228-107">[在 Lync Server 2013 中使用 Office 自訂工具 (OCT)](lync-server-2013-using-the-office-customization-tool-oct.md)來針對 Lync 及其他 Office 程式自訂安裝選項及功能。</span><span class="sxs-lookup"><span data-stu-id="85228-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="85228-108">[使用 Config.xml 執行 Lync Server 2013 中的安裝工作](lync-server-2013-using-config-xml-to-perform-installation-tasks.md)來指定網路安裝點的路徑，並執行無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="85228-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="85228-109">[Lync Server 2013 中的使用安裝程式命令列選項](lync-server-2013-using-setup-command-line-options.md)來指定要在安裝期間使用的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="85228-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="85228-110">[設定 Lync Server 2013 中的用戶端啟動載入原則](lync-server-2013-configuring-client-bootstrapping-policies.md)使用 [群組原則物件編輯器 MMC 嵌入式管理單元。</span><span class="sxs-lookup"><span data-stu-id="85228-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="85228-p102">您在部署 Office 產品套件時，可能會想設定其他選項。本節中的主題提供這些自訂工具的概觀，並說明 Lync 特定的考量。包含的連結為每個工具的詳細 Office 說明。</span><span class="sxs-lookup"><span data-stu-id="85228-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

