<sl-form>
        <sl-input name="name" type="text" label="Name" placeholder="Use a friendly name for your tank" required="true">
          <div slot="help-text">If left empty tank will be auto named, for example Tank #1, 20 gal</div>
        </sl-input>

        <br />

        <sl-select name="water" label="Water" placeholder="Select tank water type">
          <sl-menu-item value="fresh">Fresh</sl-menu-item>
          <sl-menu-item value="salt">Salt</sl-menu-item>
          <sl-menu-item value="ro">RO</sl-menu-item>
          <sl-menu-item value="distilled">Distilled</sl-menu-item>
          <sl-menu-item value="brackish">Brackish</sl-menu-item>
        </sl-select>

        <br />

        <sl-input name="size" type="number" label="Size" placeholder="Volume" required="true" min="1">
          <div slot="help-text">Tank size in gallons or liters</div>
        </sl-input>

        <br />

        <label for="sizeUnit">Size unit</label>
        <sl-radio-group class="radios">
          <sl-radio name="sizeUnit" value="gallon">gallon</sl-radio>
          <sl-radio name="sizeUnit" value="liter">liter</sl-radio>
        </sl-radio-group>

        <br />

        <sl-textarea name="notes" label="Notes" rows="2" />
      </sl-form>