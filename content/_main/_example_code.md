```php
class AcmeController
{
    public function fooAction()
    {
        /*
            Your code here.
         */
        $page = $this->get('coral.page');
        $page->setNodeByUri('/en/contact');

        return $this->render(
            $page->getNode()->getProperty('template'),
            array(
                'page'      => $page,
                'renderer'  => $this->get('coral.renderer')
            )
        );
    }
}
```