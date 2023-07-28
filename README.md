INSTALL:

composer req backend2-plus/is-mobile-bundle

Simple code for detecting device.

USE IN CONTROLLER:

    #[Route('/', name: 'app_home')]
    public function index(IsMobile $isMobile): JsonResponse
    {

        return $this->json([
            'isMobile' => $isMobile->isMobile()
        ]);
    }

USE IN TWIG:

    config/packages/twig.yaml:
    globals:
        isMobileHelper: '@IsMobile\IsMobileBundle\IsMobile'

and you can use in twig template:

    {% if isMobileHelper.IsMobile %}

    {% endif %}


